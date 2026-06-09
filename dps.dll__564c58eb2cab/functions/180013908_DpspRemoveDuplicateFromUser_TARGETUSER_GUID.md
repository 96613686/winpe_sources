# DpspRemoveDuplicateFromUser(__TARGETUSER *,_GUID *)

- ea: `0x180013908`
- end: `0x180013a07`
- name: `?DpspRemoveDuplicateFromUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct __TARGETUSER *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013148`

## callees

- `0x180001010`
- `0x180009090`
- `0x180012d2c`
- `0x180013908`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001398d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800139af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800139d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001398d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800139af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800139d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001396b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001396b`

## string_xrefs

- `0x18001393f`: `DpspRemoveDuplicateFromUser`

## pseudocode

```c
__int64 __fastcall DpspRemoveDuplicateFromUser(struct __TARGETUSER *a1, struct _GUID *a2)
{
  int v4; // r8d
  unsigned int Args; // edi
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  struct INSTANCEINFO *v7; // rbx
  __int64 v8; // rax
  struct INSTANCEINFO **v9; // rcx
  struct INSTANCEINFO *v11; // [rsp+60h] [rbp+8h] BYREF

  v11 = 0;
  if ( !a1 )
  {
    v4 = 504;
LABEL_3:
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspRemoveDuplicateFromUser",
      v4,
      (int)L"Error = %d",
      87);
    return Args;
  }
  if ( !a2 )
  {
    v4 = 505;
    goto LABEL_3;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 16));
  Args = DpspGetInstanceForUser(a1, a2, 0, &v11);
  if ( (Args & 0x80000000) == 0 )
  {
    v7 = v11;
    if ( v11 )
    {
      v8 = *(_QWORD *)v11;
      if ( *(struct INSTANCEINFO **)(*(_QWORD *)v11 + 8LL) != v11
        || (v9 = (struct INSTANCEINFO **)*((_QWORD *)v11 + 1), *v9 != v11) )
      {
        __fastfail(3u);
      }
      *v9 = (struct INSTANCEINFO *)v8;
      *(_QWORD *)(v8 + 8) = v9;
      --*((_DWORD *)a1 + 22);
      LeaveCriticalSection(v6);
      _InterlockedAnd((volatile signed __int32 *)v7 + 26, 0xFFFFFFBF);
      DpspCloseInstance(v7, 4, 15, Args);
    }
    else
    {
      LeaveCriticalSection(v6);
    }
  }
  else
  {
    LeaveCriticalSection(v6);
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspRemoveDuplicateFromUser",
      520,
      (int)L"Error = %d",
      Args);
  }
  return Args;
}

```

## disassembly

```asm
0x180013908  push    rbx
0x18001390a  push    rbp
0x18001390b  push    rsi
0x18001390c  push    rdi
0x18001390d  sub     rsp, 38h
0x180013911  mov     [rsp+58h+arg_0], 0
0x18001391a  mov     rbx, rdx
0x18001391d  mov     rsi, rcx
0x180013920  test    rcx, rcx
0x180013923  jnz     short loc_180013957
0x180013925  mov     r8d, 1F8h; int
0x18001392b  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x180013933  mov     edi, 80070057h
0x180013938  lea     r9, aErrorD; "Error = %d"
0x18001393f  lea     rdx, aDpspremovedupl; "DpspRemoveDuplicateFromUser"
0x180013946  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001394d  call    WdipTraceError
0x180013952  jmp     loc_1800139F5
0x180013957  test    rbx, rbx
0x18001395a  jnz     short loc_180013964
0x18001395c  mov     r8d, 1F9h
0x180013962  jmp     short loc_18001392B
0x180013964  lea     rbp, [rcx+10h]
0x180013968  mov     rcx, rbp; lpCriticalSection
0x18001396b  call    cs:__imp_EnterCriticalSection
0x180013971  lea     r9, [rsp+58h+arg_0]; struct INSTANCEINFO **
0x180013976  xor     r8d, r8d; unsigned int
0x180013979  mov     rdx, rbx; struct _GUID *
0x18001397c  mov     rcx, rsi; struct __TARGETUSER *
0x18001397f  call    ?DpspGetInstanceForUser@@YAJPEAU__TARGETUSER@@PEAU_GUID@@KPEAPEAUINSTANCEINFO@@@Z; DpspGetInstanceForUser(__TARGETUSER *,_GUID *,ulong,INSTANCEINFO * *)
0x180013984  mov     edi, eax
0x180013986  test    eax, eax
0x180013988  jns     short loc_1800139A2
0x18001398a  mov     rcx, rbp; lpCriticalSection
0x18001398d  call    cs:__imp_LeaveCriticalSection
0x180013993  movzx   ecx, di
0x180013996  mov     r8d, 208h
0x18001399c  mov     dword ptr [rsp+58h+Args], ecx
0x1800139a0  jmp     short loc_180013938
0x1800139a2  mov     rbx, [rsp+58h+arg_0]
0x1800139a7  test    rbx, rbx
0x1800139aa  jnz     short loc_1800139B7
0x1800139ac  mov     rcx, rbp; lpCriticalSection
0x1800139af  call    cs:__imp_LeaveCriticalSection
0x1800139b5  jmp     short loc_1800139F5
0x1800139b7  mov     rax, [rbx]
0x1800139ba  cmp     [rax+8], rbx
0x1800139be  jnz     short loc_180013A00
0x1800139c0  mov     rcx, [rbx+8]
0x1800139c4  cmp     [rcx], rbx
0x1800139c7  jnz     short loc_180013A00
0x1800139c9  mov     [rcx], rax
0x1800139cc  mov     [rax+8], rcx
0x1800139d0  mov     rcx, rbp; lpCriticalSection
0x1800139d3  dec     dword ptr [rsi+58h]
0x1800139d6  call    cs:__imp_LeaveCriticalSection
0x1800139dc  lock and dword ptr [rbx+68h], 0FFFFFFBFh
0x1800139e1  mov     edx, 4
0x1800139e6  mov     r9d, edi
0x1800139e9  mov     rcx, rbx
0x1800139ec  lea     r8d, [rdx+0Bh]
0x1800139f0  call    DpspCloseInstance
0x1800139f5  mov     eax, edi
0x1800139f7  add     rsp, 38h
0x1800139fb  pop     rdi
0x1800139fc  pop     rsi
0x1800139fd  pop     rbp
0x1800139fe  pop     rbx
0x1800139ff  retn
0x180013a00  mov     ecx, 3
0x180013a05  int     29h; Win8: RtlFailFast(ecx)
```
