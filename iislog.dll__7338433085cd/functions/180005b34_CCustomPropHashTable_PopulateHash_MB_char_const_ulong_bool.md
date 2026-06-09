# CCustomPropHashTable::PopulateHash(MB &,char const *,ulong &,bool)

- ea: `0x180005b34`
- end: `0x180005e63`
- name: `?PopulateHash@CCustomPropHashTable@@AEAAHAEAVMB@@PEBDAEAK_N@Z`
- size: `815`
- prototype: `__int64 __fastcall(CCustomPropHashTable *__hidden this, struct MB *, const char *, unsigned int *, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180004044`
- `0x180005b34`

## callees

- `0x180002410`
- `0x180005b34`
- `0x18000ec62`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `IisRTL!??0STR@@QEAA@XZ` at `0x180005b91`
- `IisRTL!??0STR@@QEAA@XZ` at `0x180005b91`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180005e38`
- `IisRTL!??1STR@@QEAA@XZ` at `0x180005e38`
- `IisRTL!PuDbgPrint` at `0x180005e14`
- `IisRTL!PuDbgPrint` at `0x180005e14`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180005bfe`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180005c18`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180005bfe`
- `IisRTL!?Append@STR@@QEAAHPEBD@Z` at `0x180005c18`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180005d9b`
- `IisRTL!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180005d9b`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005be4`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005c2c`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005d57`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005d6d`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005be4`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005c2c`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005d57`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180005d6d`
- `KERNEL32!SetLastError` at `0x180005e2d`
- `KERNEL32!SetLastError` at `0x180005e2d`

## string_xrefs

- `0x180005df6`: `inetsrv\iis\svcs\infocomm\log\plugin\extlogc.cpp`

## pseudocode

```c
__int64 __fastcall CCustomPropHashTable::PopulateHash(
        CCustomPropHashTable *this,
        struct MB *a2,
        const char *a3,
        unsigned int *a4,
        bool a5)
{
  CCustomPropHashTable *v7; // rdi
  int v8; // r13d
  unsigned int v10; // ebx
  int v11; // eax
  DWORD v12; // ecx
  int v13; // eax
  unsigned int v14; // r9d
  char *v15; // rsi
  unsigned int v16; // r9d
  unsigned int v17; // r9d
  unsigned int v18; // r9d
  __int64 v19; // rdi
  CCustomPropHashTable *v20; // rcx
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+44h] [rbp-BCh] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+4Ch] [rbp-B4h] BYREF
  CCustomPropHashTable *v26; // [rsp+50h] [rbp-B0h]
  _BYTE v27[32]; // [rsp+58h] [rbp-A8h] BYREF
  char *v28; // [rsp+78h] [rbp-88h]
  char v29; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[255]; // [rsp+91h] [rbp-6Fh] BYREF
  char v31[256]; // [rsp+190h] [rbp+90h] BYREF

  v26 = this;
  v7 = this;
  v29 = 0;
  v8 = 0;
  memset_0(v30, 0, sizeof(v30));
  STR::STR((STR *)v27);
  v10 = 1;
  while ( 1 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const char *, char *, int))(**(_QWORD **)a2 + 96LL))(
            *(_QWORD *)a2,
            *((unsigned int *)a2 + 2),
            a3,
            v31,
            v8);
    v12 = v11;
    if ( v11 < 0 )
      break;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    if ( a3 && *a3 )
    {
      if ( !STR::Copy((STR *)v27, a3) || !STR::Append((STR *)v27, "/") )
      {
LABEL_22:
        v10 = 0;
        goto LABEL_29;
      }
      v13 = STR::Append((STR *)v27, v31);
    }
    else
    {
      v13 = STR::Copy((STR *)v27, v31);
    }
    if ( !v13 )
      goto LABEL_22;
    v15 = v28;
    v29 = 0;
    v22 = 256;
    if ( (unsigned int)MB::GetData(a2, v28, 0x1196u, v14, 2u, &v29, &v22, 1u) )
    {
      v22 = 4;
      if ( (unsigned int)MB::GetData(a2, v15, 0x1197u, v16, 1u, &v23, &v22, 1u) )
      {
        v22 = 4;
        if ( (unsigned int)MB::GetData(a2, v15, 0x1198u, v17, 1u, &v24, &v22, 1u) )
        {
          v22 = 4;
          if ( (unsigned int)MB::GetData(a2, v15, 0x1199u, v18, 1u, &v25, &v22, 1u) )
          {
            if ( !a5 )
            {
              v19 = 136LL * *a4 + *((_QWORD *)v7 + 9);
              if ( !STR::Copy((STR *)v19, v15) || !STR::Copy((STR *)(v19 + 72), &v29) )
                goto LABEL_25;
              v20 = v26;
              *(_DWORD *)(v19 + 56) = v23;
              *(_DWORD *)(v19 + 60) = v24;
              *(_DWORD *)(v19 + 64) = v25;
              if ( (unsigned int)CLKRHashTable::InsertRecord(v20, v19, 0) )
              {
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\svcs\\infocomm\\log\\plugin\\extlogc.cpp",
                    267,
                    "CCustomPropHashTable::PopulateHash",
                    "PopulateHash: Unable to insert Property %s\n",
                    *(const char **)(v19 + 32));
LABEL_25:
                v10 = 0;
                goto LABEL_29;
              }
              v7 = v26;
            }
            ++*a4;
          }
        }
      }
    }
    if ( !(unsigned int)CCustomPropHashTable::PopulateHash(v7, a2, v15, a4, a5) )
      goto LABEL_22;
    ++v8;
  }
  if ( (v11 & 0x1FFF0000) == 0x70000 )
    v12 = (unsigned __int16)v11;
  SetLastError(v12);
LABEL_29:
  STR::~STR((STR *)v27);
  return v10;
}

```

## disassembly

```asm
0x180005b34  push    rbp
0x180005b36  push    rbx
0x180005b37  push    rsi
0x180005b38  push    rdi
0x180005b39  push    r12
0x180005b3b  push    r13
0x180005b3d  push    r14
0x180005b3f  push    r15
0x180005b41  lea     rbp, [rsp-1A8h]
0x180005b49  sub     rsp, 2A8h
0x180005b50  mov     rax, cs:__security_cookie
0x180005b57  xor     rax, rsp
0x180005b5a  mov     [rbp+1E0h+var_50], rax
0x180005b61  mov     r15, r8
0x180005b64  mov     [rsp+2E0h+var_290], rcx
0x180005b69  mov     r14, rdx
0x180005b6c  mov     rdi, rcx
0x180005b6f  xor     esi, esi
0x180005b71  lea     rcx, [rbp+1E0h+var_24F]; void *
0x180005b75  xor     edx, edx; Val
0x180005b77  mov     [rbp+1E0h+var_250], sil
0x180005b7b  mov     r8d, 0FFh; Size
0x180005b81  mov     r13d, esi
0x180005b84  mov     r12, r9
0x180005b87  call    memset_0
0x180005b8c  lea     rcx, [rsp+2E0h+var_288]
0x180005b91  call    cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x180005b97  lea     ebx, [rsi+1]
0x180005b9a  mov     rcx, [r14]
0x180005b9d  lea     r9, [rbp+1E0h+var_150]
0x180005ba4  mov     edx, [r14+8]
0x180005ba8  mov     r8, r15
0x180005bab  mov     dword ptr [rsp+2E0h+var_2C0], r13d
0x180005bb0  mov     rax, [rcx]
0x180005bb3  mov     rax, [rax+60h]
0x180005bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bbc  mov     ecx, eax
0x180005bbe  test    eax, eax
0x180005bc0  js      loc_180005E1E
0x180005bc6  mov     [rsp+2E0h+var_29C], esi
0x180005bca  mov     [rsp+2E0h+var_298], esi
0x180005bce  mov     [rsp+2E0h+var_294], esi
0x180005bd2  test    r15, r15
0x180005bd5  jz      short loc_180005C20
0x180005bd7  cmp     [r15], sil
0x180005bda  jz      short loc_180005C20
0x180005bdc  mov     rdx, r15
0x180005bdf  lea     rcx, [rsp+2E0h+var_288]
0x180005be4  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x180005bea  test    eax, eax
0x180005bec  jz      loc_180005DD7
0x180005bf2  lea     rdx, asc_1800131F4; "/"
0x180005bf9  lea     rcx, [rsp+2E0h+var_288]
0x180005bfe  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180005c04  test    eax, eax
0x180005c06  jz      loc_180005DD7
0x180005c0c  lea     rdx, [rbp+1E0h+var_150]
0x180005c13  lea     rcx, [rsp+2E0h+var_288]
0x180005c18  call    cs:__imp_?Append@STR@@QEAAHPEBD@Z; STR::Append(char const *)
0x180005c1e  jmp     short loc_180005C32
0x180005c20  lea     rdx, [rbp+1E0h+var_150]
0x180005c27  lea     rcx, [rsp+2E0h+var_288]
0x180005c2c  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x180005c32  test    eax, eax
0x180005c34  jz      loc_180005DD7
0x180005c3a  mov     rsi, [rsp+2E0h+var_268]
0x180005c3f  lea     rax, [rsp+2E0h+var_2A0]
0x180005c44  mov     [rsp+2E0h+var_2A8], ebx; unsigned int
0x180005c48  mov     r8d, 1196h; unsigned int
0x180005c4e  mov     [rsp+2E0h+var_2B0], rax; unsigned int *
0x180005c53  mov     rdx, rsi; char *
0x180005c56  lea     rax, [rbp+1E0h+var_250]
0x180005c5a  mov     [rbp+1E0h+var_250], 0
0x180005c5e  mov     [rsp+2E0h+var_2B8], rax; void *
0x180005c63  mov     rcx, r14; this
0x180005c66  mov     dword ptr [rsp+2E0h+var_2C0], 2; unsigned int
0x180005c6e  mov     [rsp+2E0h+var_2A0], 100h
0x180005c76  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180005c7b  test    eax, eax
0x180005c7d  jz      loc_180005DAE
0x180005c83  mov     [rsp+2E0h+var_2A8], ebx; unsigned int
0x180005c87  lea     rax, [rsp+2E0h+var_2A0]
0x180005c8c  mov     [rsp+2E0h+var_2B0], rax; unsigned int *
0x180005c91  mov     r8d, 1197h; unsigned int
0x180005c97  lea     rax, [rsp+2E0h+var_29C]
0x180005c9c  mov     [rsp+2E0h+var_2A0], 4
0x180005ca4  mov     [rsp+2E0h+var_2B8], rax; void *
0x180005ca9  mov     rdx, rsi; char *
0x180005cac  mov     rcx, r14; this
0x180005caf  mov     dword ptr [rsp+2E0h+var_2C0], ebx; unsigned int
0x180005cb3  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180005cb8  test    eax, eax
0x180005cba  jz      loc_180005DAE
0x180005cc0  mov     [rsp+2E0h+var_2A8], ebx; unsigned int
0x180005cc4  lea     rax, [rsp+2E0h+var_2A0]
0x180005cc9  mov     [rsp+2E0h+var_2B0], rax; unsigned int *
0x180005cce  mov     r8d, 1198h; unsigned int
0x180005cd4  lea     rax, [rsp+2E0h+var_298]
0x180005cd9  mov     [rsp+2E0h+var_2A0], 4
0x180005ce1  mov     [rsp+2E0h+var_2B8], rax; void *
0x180005ce6  mov     rdx, rsi; char *
0x180005ce9  mov     rcx, r14; this
0x180005cec  mov     dword ptr [rsp+2E0h+var_2C0], ebx; unsigned int
0x180005cf0  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180005cf5  test    eax, eax
0x180005cf7  jz      loc_180005DAE
0x180005cfd  mov     [rsp+2E0h+var_2A8], ebx; unsigned int
0x180005d01  lea     rax, [rsp+2E0h+var_2A0]
0x180005d06  mov     [rsp+2E0h+var_2B0], rax; unsigned int *
0x180005d0b  mov     r8d, 1199h; unsigned int
0x180005d11  lea     rax, [rsp+2E0h+var_294]
0x180005d16  mov     [rsp+2E0h+var_2A0], 4
0x180005d1e  mov     [rsp+2E0h+var_2B8], rax; void *
0x180005d23  mov     rdx, rsi; char *
0x180005d26  mov     rcx, r14; this
0x180005d29  mov     dword ptr [rsp+2E0h+var_2C0], ebx; unsigned int
0x180005d2d  call    ?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z; MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)
0x180005d32  test    eax, eax
0x180005d34  jz      short loc_180005DAE
0x180005d36  cmp     [rbp+1E0h+arg_20], 0
0x180005d3d  jnz     short loc_180005DAA
0x180005d3f  mov     eax, [r12]
0x180005d43  mov     rdx, rsi
0x180005d46  mov     rdi, [rdi+48h]
0x180005d4a  imul    rcx, rax, 88h
0x180005d51  add     rdi, rcx
0x180005d54  mov     rcx, rdi
0x180005d57  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x180005d5d  test    eax, eax
0x180005d5f  jz      loc_180005E1A
0x180005d65  lea     rcx, [rdi+48h]
0x180005d69  lea     rdx, [rbp+1E0h+var_250]
0x180005d6d  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x180005d73  test    eax, eax
0x180005d75  jz      loc_180005E1A
0x180005d7b  mov     eax, [rsp+2E0h+var_29C]
0x180005d7f  xor     r8d, r8d
0x180005d82  mov     rcx, [rsp+2E0h+var_290]
0x180005d87  mov     rdx, rdi
0x180005d8a  mov     [rdi+38h], eax
0x180005d8d  mov     eax, [rsp+2E0h+var_298]
0x180005d91  mov     [rdi+3Ch], eax
0x180005d94  mov     eax, [rsp+2E0h+var_294]
0x180005d98  mov     [rdi+40h], eax
0x180005d9b  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180005da1  test    eax, eax
0x180005da3  jnz     short loc_180005DDB
0x180005da5  mov     rdi, [rsp+2E0h+var_290]
0x180005daa  add     [r12], ebx
0x180005dae  mov     al, [rbp+1E0h+arg_20]
0x180005db4  mov     r9, r12; unsigned int *
0x180005db7  mov     r8, rsi; char *
0x180005dba  mov     [rsp+2E0h+var_2C0], al; bool
0x180005dbe  mov     rdx, r14; struct MB *
0x180005dc1  mov     rcx, rdi; this
0x180005dc4  call    ?PopulateHash@CCustomPropHashTable@@AEAAHAEAVMB@@PEBDAEAK_N@Z; CCustomPropHashTable::PopulateHash(MB &,char const *,ulong &,bool)
0x180005dc9  xor     esi, esi
0x180005dcb  test    eax, eax
0x180005dcd  jz      short loc_180005DD7
0x180005dcf  add     r13d, ebx
0x180005dd2  jmp     loc_180005B9A
0x180005dd7  mov     ebx, esi
0x180005dd9  jmp     short loc_180005E33
0x180005ddb  test    byte ptr cs:g_dwDebugFlags, 3
0x180005de2  jz      short loc_180005E1A
0x180005de4  mov     rax, [rdi+20h]
0x180005de8  lea     r9, aCcustomprophas; "CCustomPropHashTable::PopulateHash"
0x180005def  mov     rcx, cs:g_pDebug
0x180005df6  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\infocomm\\log\\plug"...
0x180005dfd  mov     [rsp+2E0h+var_2B8], rax
0x180005e02  mov     r8d, 10Bh
0x180005e08  lea     rax, aPopulatehashUn; "PopulateHash: Unable to insert Property"...
0x180005e0f  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180005e14  call    cs:__imp_PuDbgPrint
0x180005e1a  xor     ebx, ebx
0x180005e1c  jmp     short loc_180005E33
0x180005e1e  and     eax, 1FFF0000h
0x180005e23  cmp     eax, 70000h
0x180005e28  jnz     short loc_180005E2D
0x180005e2a  movzx   ecx, cx; dwErrCode
0x180005e2d  call    cs:__imp_SetLastError
0x180005e33  lea     rcx, [rsp+2E0h+var_288]
0x180005e38  call    cs:__imp_??1STR@@QEAA@XZ; STR::~STR(void)
0x180005e3e  mov     eax, ebx
0x180005e40  mov     rcx, [rbp+1E0h+var_50]
0x180005e47  xor     rcx, rsp; StackCookie
0x180005e4a  call    __security_check_cookie
0x180005e4f  add     rsp, 2A8h
0x180005e56  pop     r15
0x180005e58  pop     r14
0x180005e5a  pop     r13
0x180005e5c  pop     r12
0x180005e5e  pop     rdi
0x180005e5f  pop     rsi
0x180005e60  pop     rbx
0x180005e61  pop     rbp
0x180005e62  retn
```
