# s_GetSymmetricPopKeyTransportKeyName

- ea: `0x18000dae0`
- end: `0x18000dc58`
- name: `s_GetSymmetricPopKeyTransportKeyName`
- size: `376`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180008690`
- `0x18000b62c`
- `0x18000dae0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dbad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000dbad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dc34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000dc34`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc44`

## string_xrefs

- `0x18000db4a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`
- `0x18000dc1a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\ngcpopkeysrvrpc.c`

## pseudocode

```c
__int64 __fastcall s_GetSymmetricPopKeyTransportKeyName(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9)
{
  int PopKeyFunctionTable; // eax
  unsigned int v13; // ebx
  __int64 v14; // r9
  HLOCAL v15; // rdi
  __int64 v16; // r9
  __int64 v17; // rcx
  int v18; // eax
  HLOCAL hMem; // [rsp+40h] [rbp-48h] BYREF
  __int128 v21; // [rsp+48h] [rbp-40h] BYREF
  __int64 v22; // [rsp+58h] [rbp-30h]

  v21 = 0;
  v22 = 0;
  hMem = 0;
  PopKeyFunctionTable = CheckKeyAccessRight(a1, a2, (__int64)a5, a7, 1u, 0, 0, &hMem);
  v13 = PopKeyFunctionTable;
  if ( PopKeyFunctionTable < 0 )
  {
    v14 = 147;
LABEL_3:
    DebugTraceError(
      (unsigned int)PopKeyFunctionTable,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c",
      v14);
    goto LABEL_15;
  }
  v15 = hMem;
  if ( a5 )
    v15 = a5;
  *(_QWORD *)&v21 = a2;
  *((_QWORD *)&v21 + 1) = a3;
  v22 = a4;
  if ( !g_ngcFuncLoaded )
  {
    PopKeyFunctionTable = LoadPopKeyFunctionTable();
    v13 = PopKeyFunctionTable;
    if ( PopKeyFunctionTable < 0 )
    {
      v14 = 161;
      goto LABEL_3;
    }
  }
  AcquireSRWLockShared(&g_ngcFuncLoadLock);
  if ( !g_ngcFuncLoaded )
  {
    v13 = -2146893779;
    v16 = 172;
    v17 = 2148073517LL;
LABEL_13:
    DebugTraceError(v17, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\ngcpopkeysrvrpc.c", v16);
    goto LABEL_14;
  }
  v18 = ((__int64 (__fastcall *)(__int128 *, HLOCAL, _QWORD, _QWORD, __int64, __int64))qword_1800259A0)(
          &v21,
          v15,
          a6,
          a7,
          a8,
          a9);
  v13 = v18;
  if ( v18 < 0 )
  {
    v16 = 185;
    v17 = (unsigned int)v18;
    goto LABEL_13;
  }
LABEL_14:
  ReleaseSRWLockShared(&g_ngcFuncLoadLock);
LABEL_15:
  if ( hMem )
    LocalFree(hMem);
  return v13;
}

```

## disassembly

```asm
0x18000dae0  mov     r11, rsp
0x18000dae3  push    rbx
0x18000dae4  push    rbp
0x18000dae5  push    rdi
0x18000dae6  push    r14
0x18000dae8  push    r15
0x18000daea  sub     rsp, 60h
0x18000daee  xor     eax, eax
0x18000daf0  xorps   xmm0, xmm0
0x18000daf3  movups  [rsp+88h+var_40], xmm0
0x18000daf8  mov     [r11-30h], rax
0x18000dafc  mov     rbp, r9
0x18000daff  mov     r9d, [rsp+88h+arg_30]
0x18000db07  mov     r14, r8
0x18000db0a  mov     r8, [rsp+88h+arg_20]
0x18000db12  mov     r15, rdx
0x18000db15  mov     [r11-48h], rax
0x18000db19  lea     rax, [r11-48h]
0x18000db1d  mov     [r11-50h], rax
0x18000db21  mov     qword ptr [r11-58h], 0
0x18000db29  mov     qword ptr [r11-60h], 0
0x18000db31  mov     dword ptr [rsp+88h+var_68], 1
0x18000db39  call    CheckKeyAccessRight
0x18000db3e  mov     ebx, eax
0x18000db40  test    eax, eax
0x18000db42  jns     short loc_18000DB64
0x18000db44  mov     r9d, 93h
0x18000db4a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000db51  mov     ecx, eax
0x18000db53  lea     rdx, aHr; "hr"
0x18000db5a  call    DebugTraceError
0x18000db5f  jmp     loc_18000DC3A
0x18000db64  cmp     [rsp+88h+arg_20], 0
0x18000db6d  mov     rdi, [rsp+88h+hMem]
0x18000db72  cmovnz  rdi, [rsp+88h+arg_20]
0x18000db7b  cmp     cs:g_ngcFuncLoaded, 0
0x18000db82  mov     qword ptr [rsp+88h+var_40], r15
0x18000db87  mov     qword ptr [rsp+88h+var_40+8], r14
0x18000db8c  mov     [rsp+88h+var_30], rbp
0x18000db91  jnz     short loc_18000DBA6
0x18000db93  call    LoadPopKeyFunctionTable
0x18000db98  mov     ebx, eax
0x18000db9a  test    eax, eax
0x18000db9c  jns     short loc_18000DBA6
0x18000db9e  mov     r9d, 0A1h
0x18000dba4  jmp     short loc_18000DB4A
0x18000dba6  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000dbad  call    cs:__imp_AcquireSRWLockShared
0x18000dbb3  cmp     cs:g_ngcFuncLoaded, 0
0x18000dbba  jnz     short loc_18000DBCE
0x18000dbbc  mov     ebx, 8009002Dh
0x18000dbc1  mov     r9d, 0ACh
0x18000dbc7  mov     ecx, 8009002Dh
0x18000dbcc  jmp     short loc_18000DC1A
0x18000dbce  mov     rcx, [rsp+88h+arg_40]
0x18000dbd6  mov     rdx, rdi
0x18000dbd9  mov     r9d, [rsp+88h+arg_30]
0x18000dbe1  mov     r8d, [rsp+88h+arg_28]
0x18000dbe9  mov     rax, cs:qword_1800259A0
0x18000dbf0  mov     [rsp+88h+var_60], rcx
0x18000dbf5  mov     rcx, [rsp+88h+arg_38]
0x18000dbfd  mov     [rsp+88h+var_68], rcx
0x18000dc02  lea     rcx, [rsp+88h+var_40]
0x18000dc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc0c  mov     ebx, eax
0x18000dc0e  test    eax, eax
0x18000dc10  jns     short loc_18000DC2D
0x18000dc12  mov     r9d, 0B9h
0x18000dc18  mov     ecx, eax
0x18000dc1a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dc21  lea     rdx, aHr; "hr"
0x18000dc28  call    DebugTraceError
0x18000dc2d  lea     rcx, g_ngcFuncLoadLock; SRWLock
0x18000dc34  call    cs:__imp_ReleaseSRWLockShared
0x18000dc3a  mov     rcx, [rsp+88h+hMem]; hMem
0x18000dc3f  test    rcx, rcx
0x18000dc42  jz      short loc_18000DC4A
0x18000dc44  call    cs:__imp_LocalFree
0x18000dc4a  mov     eax, ebx
0x18000dc4c  add     rsp, 60h
0x18000dc50  pop     r15
0x18000dc52  pop     r14
0x18000dc54  pop     rdi
0x18000dc55  pop     rbp
0x18000dc56  pop     rbx
0x18000dc57  retn
```
