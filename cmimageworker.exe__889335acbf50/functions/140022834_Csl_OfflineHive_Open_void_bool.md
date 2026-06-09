# Csl::OfflineHive::Open(void *,bool)

- ea: `0x140022834`
- end: `0x1400228f4`
- name: `?Open@OfflineHive@Csl@@QEAAJPEAX_N@Z`
- size: `192`
- prototype: `__int64 __fastcall(Csl::OfflineHive *this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001adb0`

## callees

- `0x14000d7bc`
- `0x140022834`
- `0x140022ed0`
- `0x140023544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400228c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400228c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400228ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400228ac`

## string_xrefs

- `0x140022867`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::Open(Csl::OfflineHive *this, void *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  unsigned int *v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // rsi
  DWORD LastError; // ebx
  __int64 v10; // rcx
  unsigned int v11[14]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)v11 = 0;
  v3 = OROpenHiveInternal(a2);
  if ( v3 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x8E,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v3,
           v11[0]);
    if ( *(_QWORD *)v11 )
      ORCloseHive(*(_QWORD *)v11);
    return v4;
  }
  else
  {
    *(_BYTE *)this = 0;
    v6 = (unsigned int *)((char *)this + 8);
    if ( v6 == v11 )
    {
      v10 = *(_QWORD *)v11;
    }
    else
    {
      v7 = *(_QWORD *)v11;
      v8 = *(_QWORD *)v6;
      if ( *(_QWORD *)v6 )
      {
        LastError = GetLastError();
        ORCloseHive(v8);
        SetLastError(LastError);
      }
      *(_QWORD *)v6 = v7;
      v10 = 0;
    }
    if ( v10 )
      ORCloseHive(v10);
    return 0;
  }
}

```

## disassembly

```asm
0x140022834  push    rbx
0x140022836  push    rbp
0x140022837  push    rsi
0x140022838  push    rdi
0x140022839  sub     rsp, 38h
0x14002283d  mov     rax, rdx
0x140022840  mov     rdi, rcx
0x140022843  mov     qword ptr [rsp+58h+var_38], 0; unsigned int
0x14002284c  lea     r9, [rsp+58h+var_38]
0x140022851  xor     edx, edx
0x140022853  mov     rcx, rax; hFile
0x140022856  call    OROpenHiveInternal
0x14002285b  test    eax, eax
0x14002285d  jz      short loc_14002288E
0x14002285f  mov     rcx, [rsp+58h]; this
0x140022864  mov     r9d, eax; char *
0x140022867  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14002286e  mov     edx, 8Eh; void *
0x140022873  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140022878  mov     ebx, eax
0x14002287a  mov     rcx, qword ptr [rsp+58h+var_38]
0x14002287f  test    rcx, rcx
0x140022882  jz      short loc_14002288A
0x140022884  call    ORCloseHive
0x140022889  nop
0x14002288a  mov     eax, ebx
0x14002288c  jmp     short loc_1400228EA
0x14002288e  mov     byte ptr [rdi], 0
0x140022891  add     rdi, 8
0x140022895  lea     rax, [rsp+58h+var_38]
0x14002289a  cmp     rdi, rax
0x14002289d  jz      short loc_1400228D8
0x14002289f  mov     rbp, qword ptr [rsp+58h+var_38]
0x1400228a4  mov     rsi, [rdi]
0x1400228a7  test    rsi, rsi
0x1400228aa  jz      short loc_1400228D1
0x1400228ac  call    cs:__imp_GetLastError
0x1400228b3  nop     dword ptr [rax+rax+00h]
0x1400228b8  mov     ebx, eax
0x1400228ba  mov     rcx, rsi
0x1400228bd  call    ORCloseHive
0x1400228c2  mov     ecx, ebx; dwErrCode
0x1400228c4  call    cs:__imp_SetLastError
0x1400228cb  nop     dword ptr [rax+rax+00h]
0x1400228d0  nop
0x1400228d1  mov     [rdi], rbp
0x1400228d4  xor     ecx, ecx
0x1400228d6  jmp     short loc_1400228DD
0x1400228d8  mov     rcx, qword ptr [rsp+58h+var_38]
0x1400228dd  test    rcx, rcx
0x1400228e0  jz      short loc_1400228E8
0x1400228e2  call    ORCloseHive
0x1400228e7  nop
0x1400228e8  xor     eax, eax
0x1400228ea  add     rsp, 38h
0x1400228ee  pop     rdi
0x1400228ef  pop     rsi
0x1400228f0  pop     rbp
0x1400228f1  pop     rbx
0x1400228f2  retn
```
