# DpspRemoveInstanceFromUser(__TARGETUSER *,_GUID *,int *)

- ea: `0x180013a10`
- end: `0x180013b45`
- name: `?DpspRemoveInstanceFromUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@PEAH@Z`
- size: `309`
- prototype: `__int64 __fastcall(struct __TARGETUSER *, struct _GUID *, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180012e2c`
- `0x1800146b0`
- `0x180015918`

## callees

- `0x180001010`
- `0x180009090`
- `0x180012d2c`
- `0x180013a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ab8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013add`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a93`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a93`

## string_xrefs

- `0x180013a53`: `DpspRemoveInstanceFromUser`

## pseudocode

```c
__int64 __fastcall DpspRemoveInstanceFromUser(struct __TARGETUSER *a1, struct _GUID *a2, int *a3)
{
  int v6; // r8d
  unsigned int Args; // ebx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  struct INSTANCEINFO *v9; // rdi
  __int64 v10; // rcx
  struct INSTANCEINFO **v11; // rax
  struct INSTANCEINFO *v13; // [rsp+50h] [rbp+8h] BYREF

  v13 = 0;
  if ( !a1 )
  {
    v6 = 430;
LABEL_3:
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspRemoveInstanceFromUser",
      v6,
      (int)L"Error = %d",
      87);
    return Args;
  }
  if ( !a2 )
  {
    v6 = 431;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = 432;
    goto LABEL_3;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 16);
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  Args = DpspGetInstanceForUser(a1, a2, 1u, &v13);
  if ( (Args & 0x80000000) == 0 )
  {
    v9 = v13;
    if ( v13 )
    {
      v10 = *(_QWORD *)v13;
      *a3 = 1;
      if ( *(struct INSTANCEINFO **)(v10 + 8) != v9 || (v11 = (struct INSTANCEINFO **)*((_QWORD *)v9 + 1), *v11 != v9) )
        __fastfail(3u);
      *v11 = (struct INSTANCEINFO *)v10;
      *(_QWORD *)(v10 + 8) = v11;
      --*((_DWORD *)a1 + 22);
      LeaveCriticalSection(v8);
      _InterlockedAnd((volatile signed __int32 *)v9 + 26, 0xFFFFFFBF);
      DpspCloseInstance(v9, 4, 15, Args);
    }
    else
    {
      LeaveCriticalSection(v8);
    }
  }
  else
  {
    LeaveCriticalSection(v8);
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspRemoveInstanceFromUser",
      445,
      (int)L"Error = %d",
      Args);
  }
  return Args;
}

```

## disassembly

```asm
0x180013a10  mov     [rsp+arg_8], rbx
0x180013a15  mov     [rsp+arg_10], rbp
0x180013a1a  push    rsi
0x180013a1b  push    rdi
0x180013a1c  push    r14
0x180013a1e  sub     rsp, 30h
0x180013a22  mov     [rsp+48h+arg_0], 0
0x180013a2b  mov     rsi, r8
0x180013a2e  mov     rbx, rdx
0x180013a31  mov     rbp, rcx
0x180013a34  test    rcx, rcx
0x180013a37  jnz     short loc_180013A6B
0x180013a39  mov     r8d, 1AEh; int
0x180013a3f  mov     ebx, 80070057h
0x180013a44  mov     dword ptr [rsp+48h+Args], 57h ; 'W'; Args
0x180013a4c  lea     r9, aErrorD; "Error = %d"
0x180013a53  lea     rdx, aDpspremoveinst; "DpspRemoveInstanceFromUser"
0x180013a5a  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180013a61  call    WdipTraceError
0x180013a66  jmp     loc_180013B29
0x180013a6b  test    rbx, rbx
0x180013a6e  jnz     short loc_180013A78
0x180013a70  mov     r8d, 1AFh
0x180013a76  jmp     short loc_180013A3F
0x180013a78  test    rsi, rsi
0x180013a7b  jnz     short loc_180013A85
0x180013a7d  mov     r8d, 1B0h
0x180013a83  jmp     short loc_180013A3F
0x180013a85  lea     r14, [rcx+10h]
0x180013a89  mov     dword ptr [r8], 0
0x180013a90  mov     rcx, r14; lpCriticalSection
0x180013a93  call    cs:__imp_EnterCriticalSection
0x180013a99  lea     r9, [rsp+48h+arg_0]; struct INSTANCEINFO **
0x180013a9e  mov     r8d, 1; unsigned int
0x180013aa4  mov     rdx, rbx; struct _GUID *
0x180013aa7  mov     rcx, rbp; struct __TARGETUSER *
0x180013aaa  call    ?DpspGetInstanceForUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@KPEAPEAUINSTANCEINFO@@@Z; DpspGetInstanceForUser(__TARGETUSER *,_GUID *,ulong,INSTANCEINFO * *)
0x180013aaf  mov     ebx, eax
0x180013ab1  test    eax, eax
0x180013ab3  jns     short loc_180013AD0
0x180013ab5  mov     rcx, r14; lpCriticalSection
0x180013ab8  call    cs:__imp_LeaveCriticalSection
0x180013abe  movzx   ecx, bx
0x180013ac1  mov     r8d, 1BDh
0x180013ac7  mov     dword ptr [rsp+48h+Args], ecx
0x180013acb  jmp     loc_180013A4C
0x180013ad0  mov     rdi, [rsp+48h+arg_0]
0x180013ad5  test    rdi, rdi
0x180013ad8  jnz     short loc_180013AE5
0x180013ada  mov     rcx, r14; lpCriticalSection
0x180013add  call    cs:__imp_LeaveCriticalSection
0x180013ae3  jmp     short loc_180013B29
0x180013ae5  mov     rcx, [rdi]
0x180013ae8  mov     dword ptr [rsi], 1
0x180013aee  cmp     [rcx+8], rdi
0x180013af2  jnz     short loc_180013B3E
0x180013af4  mov     rax, [rdi+8]
0x180013af8  cmp     [rax], rdi
0x180013afb  jnz     short loc_180013B3E
0x180013afd  mov     [rax], rcx
0x180013b00  mov     [rcx+8], rax
0x180013b04  mov     rcx, r14; lpCriticalSection
0x180013b07  dec     dword ptr [rbp+58h]
0x180013b0a  call    cs:__imp_LeaveCriticalSection
0x180013b10  lock and dword ptr [rdi+68h], 0FFFFFFBFh
0x180013b15  mov     edx, 4
0x180013b1a  mov     r9d, ebx
0x180013b1d  mov     rcx, rdi
0x180013b20  lea     r8d, [rdx+0Bh]
0x180013b24  call    DpspCloseInstance
0x180013b29  mov     rbp, [rsp+48h+arg_10]
0x180013b2e  mov     eax, ebx
0x180013b30  mov     rbx, [rsp+48h+arg_8]
0x180013b35  add     rsp, 30h
0x180013b39  pop     r14
0x180013b3b  pop     rdi
0x180013b3c  pop     rsi
0x180013b3d  retn
0x180013b3e  mov     ecx, 3
0x180013b43  int     29h; Win8: RtlFailFast(ecx)
```
