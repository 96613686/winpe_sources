# DecomposeDescriptor(ushort const *,bool,ushort *,ushort *,ushort *,ulong *,ulong *,bool *)

- ea: `0x18004a07c`
- end: `0x18004a527`
- name: `?DecomposeDescriptor@@YAHPEBG_NPEAG22PEAK3PEA_N@Z`
- size: `1195`
- prototype: `int(const unsigned __int16 *, bool, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *, bool *)`
- caller_count: `13`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041d34`
- `0x180042810`
- `0x180044560`
- `0x180045c60`
- `0x180049774`
- `0x18004bb30`
- `0x18009e6c0`
- `0x18015c880`
- `0x18019bd10`
- `0x18019c100`
- `0x18019ea08`
- `0x1801a0fe0`
- `0x1801a1710`

## callees

- `0x18000c4bc`
- `0x18003bd60`
- `0x1800493f0`
- `0x18004a07c`
- `0x180265240`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18004a0e9`
- `KERNEL32!lstrlenW` at `0x18004a0e9`
- `KERNEL32!GlobalFree` at `0x18004a1e6`
- `KERNEL32!GlobalFree` at `0x18004a208`
- `KERNEL32!GlobalFree` at `0x18004a2a6`
- `KERNEL32!GlobalFree` at `0x18004a2c8`
- `KERNEL32!GlobalFree` at `0x18004a407`
- `KERNEL32!GlobalFree` at `0x18004a42e`
- `KERNEL32!GlobalFree` at `0x18004a1e6`
- `KERNEL32!GlobalFree` at `0x18004a208`
- `KERNEL32!GlobalFree` at `0x18004a2a6`
- `KERNEL32!GlobalFree` at `0x18004a2c8`
- `KERNEL32!GlobalFree` at `0x18004a407`
- `KERNEL32!GlobalFree` at `0x18004a42e`

## string_xrefs

- `0x18004a3b4`: `MSI_DBG: Provided descriptor less than minimum size`
- `0x18004a442`: `MSI_DBG: Invalid descriptor format - unable to decode ProductCode in descriptor`
- `0x18004a45b`: `MSI_DBG: Invalid feature name provided in descriptor (exceeds max feature length)`
- `0x18004a302`: `MSI_DBG: Invalid descriptor format`
- `0x18004a499`: `MSI_DBG: Descriptor feature validation failed`
- `0x18004a4ee`: `MSI_DBG: Descriptor feature validation failed`
- `0x18004a38c`: `MSI_DBG: Invalid descriptor format - missing component specification`
- `0x18004a376`: `MSI_DBG: Invalid descriptor format - unable to decode component`

## pseudocode

```c
__int64 __fastcall DecomposeDescriptor(
        const unsigned __int16 *a1,
        char a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        unsigned int *a7,
        bool *a8)
{
  int v11; // edi
  const WCHAR *v12; // rbx
  WCHAR *v13; // rax
  bool *v14; // rcx
  int v15; // esi
  bool v16; // zf
  const unsigned __int16 *v17; // r14
  WCHAR *v18; // r10
  int v19; // ecx
  WCHAR *v20; // r14
  LPWSTR v21; // r8
  int i; // esi
  _WORD *v24; // rbx
  __int64 v25; // rbx
  const unsigned __int16 *v26; // r9
  char v27; // [rsp+60h] [rbp-A0h] BYREF
  char v28; // [rsp+61h] [rbp-9Fh]
  LPWSTR lpFeatureBuf; // [rsp+68h] [rbp-98h]
  bool *v30; // [rsp+70h] [rbp-90h]
  unsigned int *v31; // [rsp+78h] [rbp-88h]
  unsigned int *v32; // [rsp+80h] [rbp-80h]
  HGLOBAL hMem; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+98h] [rbp-68h]
  _BYTE v35[80]; // [rsp+A0h] [rbp-60h] BYREF
  HGLOBAL v36; // [rsp+F0h] [rbp-10h]
  int v37; // [rsp+F8h] [rbp-8h]
  _BYTE v38[80]; // [rsp+100h] [rbp+0h] BYREF
  HGLOBAL v39; // [rsp+150h] [rbp+50h]
  int v40; // [rsp+158h] [rbp+58h]
  WCHAR FeatureBuf[40]; // [rsp+160h] [rbp+60h] BYREF

  v31 = a6;
  v32 = a7;
  v28 = a2;
  if ( a1 )
  {
    v11 = lstrlenW(a1);
    if ( v11 < 20 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"MSI_DBG: Provided descriptor less than minimum size",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
    }
    else
    {
      v27 = 0;
      v37 = 39;
      v34 = 39;
      v36 = v38;
      v12 = (const WCHAR *)v38;
      if ( a3 )
        v12 = a3;
      hMem = v35;
      v13 = (WCHAR *)v35;
      if ( a4 )
        v13 = a4;
      v14 = (bool *)&v27;
      lpFeatureBuf = v13;
      v15 = v11 - 1;
      if ( a8 )
        v14 = a8;
      v16 = *a1 == 124;
      v30 = v14;
      if ( !v16 )
        v15 = v11;
      v17 = a1 + 1;
      if ( !v16 )
        v17 = a1;
      *v14 = v16;
      if ( (unsigned int)UnpackGUID(v17, v12, 39, 2) )
      {
        v18 = lpFeatureBuf;
        v19 = 38;
        v20 = (WCHAR *)(v17 + 20);
        v21 = lpFeatureBuf;
        for ( i = v15 - 20; ; --i )
        {
          if ( i <= 0 )
          {
            if ( !g_dmDiagnosticMode )
              goto LABEL_20;
            v26 = L"MSI_DBG: Invalid descriptor format";
            goto LABEL_41;
          }
          if ( ((*v20 - 60) & 0xFFFD) == 0 )
          {
            if ( v20 - a1 == *v30 + 20LL )
            {
              if ( v28 )
              {
                if ( MsiEnumFeaturesW(v12, 0, v18, 0) )
                {
                  if ( g_dmDiagnosticMode )
                    DebugString(
                      10,
                      0,
                      0,
                      L"MSI_DBG: Descriptor feature validation failed",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      0,
                      0);
                  goto LABEL_20;
                }
                v40 = 39;
                v39 = FeatureBuf;
                if ( MsiEnumFeaturesW(v12, 1u, FeatureBuf, 0) != 259 )
                {
                  if ( g_dmDiagnosticMode )
                    DebugString(
                      10,
                      0,
                      0,
                      L"MSI_DBG: Descriptor feature validation failed",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      L"(NULL)",
                      0,
                      0);
                  if ( v40 > 39 )
                    GlobalFree(v39);
                  v40 = 39;
                  v39 = FeatureBuf;
                  goto LABEL_20;
                }
                if ( v40 > 39 )
                  GlobalFree(v39);
              }
            }
            else
            {
              *v21 = 0;
            }
            v24 = v20 + 1;
            if ( *v20 == 62 )
            {
              if ( i - 1 < 20 )
              {
                if ( !g_dmDiagnosticMode )
                  goto LABEL_20;
                v26 = L"MSI_DBG: Invalid descriptor format - missing component specification";
                goto LABEL_41;
              }
              if ( a5 && !(unsigned int)UnpackGUID(v20 + 1, a5, 39, 2) )
              {
                if ( !g_dmDiagnosticMode )
                  goto LABEL_20;
                v26 = L"MSI_DBG: Invalid descriptor format - unable to decode component";
                goto LABEL_41;
              }
              v24 = v20 + 21;
            }
            else if ( a5 )
            {
              *a5 = 0;
            }
            if ( v31 )
            {
              v25 = v24 - a1;
              *v31 = v25;
              if ( v32 )
                *v32 = v11 - v25;
            }
            if ( v34 > 39 )
              GlobalFree(hMem);
            v34 = 39;
            hMem = v35;
            if ( v37 > 39 )
              GlobalFree(v36);
            return 1;
          }
          if ( !v19 )
            break;
          *v21 = *v20;
          --v19;
          ++v21;
          ++v20;
        }
        if ( !g_dmDiagnosticMode )
          goto LABEL_20;
        v26 = L"MSI_DBG: Invalid feature name provided in descriptor (exceeds max feature length)";
LABEL_41:
        DebugString(10, 0, 0, v26, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
      }
      else if ( g_dmDiagnosticMode )
      {
        v26 = L"MSI_DBG: Invalid descriptor format - unable to decode ProductCode in descriptor";
        goto LABEL_41;
      }
LABEL_20:
      if ( v34 > 39 )
        GlobalFree(hMem);
      v34 = 39;
      hMem = v35;
      if ( v37 > 39 )
        GlobalFree(v36);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004a07c  mov     [rsp-8+arg_8], rbx
0x18004a081  push    rbp
0x18004a082  push    rsi
0x18004a083  push    rdi
0x18004a084  push    r12
0x18004a086  push    r13
0x18004a088  push    r14
0x18004a08a  push    r15
0x18004a08c  lea     rbp, [rsp-0C0h]
0x18004a094  sub     rsp, 1C0h
0x18004a09b  mov     rax, cs:__security_cookie
0x18004a0a2  xor     rax, rsp
0x18004a0a5  mov     [rbp+0F0h+var_40], rax
0x18004a0ac  mov     rax, [rbp+0F0h+arg_28]
0x18004a0b3  xor     ebx, ebx
0x18004a0b5  mov     r13, [rbp+0F0h+arg_38]
0x18004a0bc  mov     r14, r9
0x18004a0bf  mov     r15, [rbp+0F0h+arg_20]
0x18004a0c6  mov     rsi, r8
0x18004a0c9  mov     [rsp+1F0h+var_178], rax
0x18004a0ce  mov     r12, rcx
0x18004a0d1  mov     rax, [rbp+0F0h+arg_30]
0x18004a0d8  mov     [rbp+0F0h+var_170], rax
0x18004a0dc  mov     [rsp+1F0h+var_18F], dl
0x18004a0e0  test    rcx, rcx
0x18004a0e3  jz      loc_18004A214
0x18004a0e9  call    cs:__imp_lstrlenW
0x18004a0f0  nop     dword ptr [rax+rax+00h]
0x18004a0f5  mov     edi, eax
0x18004a0f7  cmp     eax, 14h
0x18004a0fa  jl      loc_18004A398
0x18004a100  lea     ecx, [rbx+27h]
0x18004a103  mov     [rsp+1F0h+var_190], bl
0x18004a107  test    rsi, rsi
0x18004a10a  mov     [rbp+0F0h+var_F8], ecx
0x18004a10d  lea     rax, [rbp+0F0h+var_F0]
0x18004a111  mov     [rbp+0F0h+var_158], ecx
0x18004a114  mov     [rbp+0F0h+var_100], rax
0x18004a118  lea     rbx, [rbp+0F0h+var_F0]
0x18004a11c  cmovnz  rbx, rsi
0x18004a120  lea     rax, [rbp+0F0h+var_150]
0x18004a124  test    r14, r14
0x18004a127  mov     [rbp+0F0h+hMem], rax
0x18004a12b  lea     rax, [rbp+0F0h+var_150]
0x18004a12f  cmovnz  rax, r14
0x18004a133  lea     rcx, [rsp+1F0h+var_190]
0x18004a138  test    r13, r13
0x18004a13b  mov     [rsp+1F0h+lpFeatureBuf], rax
0x18004a140  lea     esi, [rdi-1]
0x18004a143  cmovnz  rcx, r13
0x18004a147  cmp     word ptr [r12], 7Ch ; '|'
0x18004a14d  mov     [rsp+1F0h+var_180], rcx
0x18004a152  jz      short loc_18004A156
0x18004a154  mov     esi, edi
0x18004a156  mov     r9d, 2
0x18004a15c  lea     r14, [r12+2]
0x18004a161  setz    al
0x18004a164  cmovnz  r14, r12
0x18004a168  mov     [rcx], al
0x18004a16a  mov     rdx, rbx
0x18004a16d  mov     rcx, r14
0x18004a170  lea     r13d, [r9+25h]
0x18004a174  mov     r8d, r13d
0x18004a177  call    ?UnpackGUID@@YA?AW4Bool@@PEBGPEAGKW4ipgEnum@@@Z; UnpackGUID(ushort const *,ushort *,ulong,ipgEnum)
0x18004a17c  xor     r11d, r11d
0x18004a17f  test    eax, eax
0x18004a181  jz      short loc_18004A1CF
0x18004a183  mov     r10, [rsp+1F0h+lpFeatureBuf]
0x18004a188  lea     ecx, [r13-1]
0x18004a18c  add     r14, 28h ; '('
0x18004a190  mov     r8, r10
0x18004a193  sub     esi, 14h
0x18004a196  test    esi, esi
0x18004a198  jle     loc_18004A2F5
0x18004a19e  movzx   edx, word ptr [r14]
0x18004a1a2  mov     r9d, 0FFFDh
0x18004a1a8  lea     eax, [rdx-3Ch]
0x18004a1ab  test    r9w, ax
0x18004a1af  jz      loc_18004A241
0x18004a1b5  test    ecx, ecx
0x18004a1b7  jz      loc_18004A44E
0x18004a1bd  mov     [r8], dx
0x18004a1c1  dec     ecx
0x18004a1c3  add     r8, 2
0x18004a1c7  add     r14, 2
0x18004a1cb  dec     esi
0x18004a1cd  jmp     short loc_18004A196
0x18004a1cf  cmp     cs:?g_dmDiagnosticMode@@3HA, r11d; int g_dmDiagnosticMode
0x18004a1d6  jnz     loc_18004A442
0x18004a1dc  cmp     [rbp+0F0h+var_158], r13d
0x18004a1e0  jle     short loc_18004A1F2
0x18004a1e2  mov     rcx, [rbp+0F0h+hMem]; hMem
0x18004a1e6  call    cs:__imp_GlobalFree
0x18004a1ed  nop     dword ptr [rax+rax+00h]
0x18004a1f2  lea     rax, [rbp+0F0h+var_150]
0x18004a1f6  mov     [rbp+0F0h+var_158], r13d
0x18004a1fa  mov     [rbp+0F0h+hMem], rax
0x18004a1fe  cmp     [rbp+0F0h+var_F8], r13d
0x18004a202  jle     short loc_18004A214
0x18004a204  mov     rcx, [rbp+0F0h+var_100]; hMem
0x18004a208  call    cs:__imp_GlobalFree
0x18004a20f  nop     dword ptr [rax+rax+00h]
0x18004a214  xor     eax, eax
0x18004a216  mov     rcx, [rbp+0F0h+var_40]
0x18004a21d  xor     rcx, rsp; StackCookie
0x18004a220  call    __security_check_cookie
0x18004a225  mov     rbx, [rsp+1F0h+arg_8]
0x18004a22d  add     rsp, 1C0h
0x18004a234  pop     r15
0x18004a236  pop     r14
0x18004a238  pop     r13
0x18004a23a  pop     r12
0x18004a23c  pop     rdi
0x18004a23d  pop     rsi
0x18004a23e  pop     rbp
0x18004a23f  retn
0x18004a241  mov     rax, [rsp+1F0h+var_180]
0x18004a246  mov     rdx, r14
0x18004a249  sub     rdx, r12
0x18004a24c  sar     rdx, 1
0x18004a24f  mov     al, [rax]
0x18004a251  neg     al
0x18004a253  sbb     rcx, rcx
0x18004a256  neg     rcx
0x18004a259  add     rcx, 14h
0x18004a25d  cmp     rdx, rcx
0x18004a260  jz      loc_18004A467
0x18004a266  mov     [r8], r11w
0x18004a26a  cmp     word ptr [r14], 3Eh ; '>'
0x18004a26f  lea     rbx, [r14+2]
0x18004a273  jnz     loc_18004A3EB
0x18004a279  lea     eax, [rsi-1]
0x18004a27c  cmp     eax, 14h
0x18004a27f  jl      loc_18004A37F
0x18004a285  test    r15, r15
0x18004a288  jnz     loc_18004A34A
0x18004a28e  add     rbx, 28h ; '('
0x18004a292  mov     rax, [rsp+1F0h+var_178]
0x18004a297  test    rax, rax
0x18004a29a  jnz     short loc_18004A2DE
0x18004a29c  cmp     [rbp+0F0h+var_158], r13d
0x18004a2a0  jle     short loc_18004A2B2
0x18004a2a2  mov     rcx, [rbp+0F0h+hMem]; hMem
0x18004a2a6  call    cs:__imp_GlobalFree
0x18004a2ad  nop     dword ptr [rax+rax+00h]
0x18004a2b2  lea     rcx, [rbp+0F0h+var_150]
0x18004a2b6  mov     [rbp+0F0h+var_158], r13d
0x18004a2ba  mov     [rbp+0F0h+hMem], rcx
0x18004a2be  cmp     [rbp+0F0h+var_F8], r13d
0x18004a2c2  jle     short loc_18004A2D4
0x18004a2c4  mov     rcx, [rbp+0F0h+var_100]; hMem
0x18004a2c8  call    cs:__imp_GlobalFree
0x18004a2cf  nop     dword ptr [rax+rax+00h]
0x18004a2d4  mov     eax, 1
0x18004a2d9  jmp     loc_18004A216
0x18004a2de  sub     rbx, r12
0x18004a2e1  sar     rbx, 1
0x18004a2e4  mov     [rax], ebx
0x18004a2e6  mov     rax, [rbp+0F0h+var_170]
0x18004a2ea  test    rax, rax
0x18004a2ed  jz      short loc_18004A29C
0x18004a2ef  sub     edi, ebx
0x18004a2f1  mov     [rax], edi
0x18004a2f3  jmp     short loc_18004A29C
0x18004a2f5  cmp     cs:?g_dmDiagnosticMode@@3HA, r11d; int g_dmDiagnosticMode
0x18004a2fc  jz      loc_18004A1DC
0x18004a302  lea     r9, aMsiDbgInvalidD_2; "MSI_DBG: Invalid descriptor format"
0x18004a309  mov     [rsp+1F0h+var_198], r11; void *
0x18004a30e  mov     [rsp+1F0h+var_1A0], r11d; unsigned int
0x18004a313  lea     rax, aNull; "(NULL)"
0x18004a31a  xor     edx, edx; unsigned __int16
0x18004a31c  mov     [rsp+1F0h+var_1A8], rax; unsigned __int16 *
0x18004a321  xor     r8d, r8d; int
0x18004a324  mov     [rsp+1F0h+var_1B0], rax; unsigned __int16 *
0x18004a329  mov     [rsp+1F0h+var_1B8], rax; unsigned __int16 *
0x18004a32e  mov     [rsp+1F0h+var_1C0], rax; unsigned __int16 *
0x18004a333  lea     ecx, [rdx+0Ah]; int
0x18004a336  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x18004a33b  mov     [rsp+1F0h+var_1D0], rax; unsigned __int16 *
0x18004a340  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004a345  jmp     loc_18004A1DC
0x18004a34a  mov     r9d, 2
0x18004a350  mov     r8d, r13d
0x18004a353  mov     rdx, r15
0x18004a356  mov     rcx, rbx
0x18004a359  call    ?UnpackGUID@@YA?AW4Bool@@PEBGPEAGKW4ipgEnum@@@Z; UnpackGUID(ushort const *,ushort *,ulong,ipgEnum)
0x18004a35e  xor     r11d, r11d
0x18004a361  test    eax, eax
0x18004a363  jnz     loc_18004A28E
0x18004a369  cmp     cs:?g_dmDiagnosticMode@@3HA, r11d; int g_dmDiagnosticMode
0x18004a370  jz      loc_18004A1DC
0x18004a376  lea     r9, aMsiDbgInvalidD; "MSI_DBG: Invalid descriptor format - un"...
0x18004a37d  jmp     short loc_18004A309
0x18004a37f  cmp     cs:?g_dmDiagnosticMode@@3HA, r11d; int g_dmDiagnosticMode
0x18004a386  jz      loc_18004A1DC
0x18004a38c  lea     r9, aMsiDbgInvalidD_0; "MSI_DBG: Invalid descriptor format - mi"...
0x18004a393  jmp     loc_18004A309
0x18004a398  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x18004a39e  jz      loc_18004A214
0x18004a3a4  mov     [rsp+1F0h+var_198], rbx; void *
0x18004a3a9  lea     rax, aNull; "(NULL)"
0x18004a3b0  mov     [rsp+1F0h+var_1A0], ebx; unsigned int
0x18004a3b4  lea     r9, aMsiDbgProvided; "MSI_DBG: Provided descriptor less than "...
0x18004a3bb  mov     [rsp+1F0h+var_1A8], rax; unsigned __int16 *
0x18004a3c0  xor     edx, edx; unsigned __int16
0x18004a3c2  mov     [rsp+1F0h+var_1B0], rax; unsigned __int16 *
0x18004a3c7  xor     r8d, r8d; int
0x18004a3ca  mov     [rsp+1F0h+var_1B8], rax; unsigned __int16 *
0x18004a3cf  mov     [rsp+1F0h+var_1C0], rax; unsigned __int16 *
0x18004a3d4  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x18004a3d9  lea     ecx, [rdx+0Ah]; int
0x18004a3dc  mov     [rsp+1F0h+var_1D0], rax; unsigned __int16 *
0x18004a3e1  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004a3e6  jmp     loc_18004A214
0x18004a3eb  test    r15, r15
0x18004a3ee  jz      loc_18004A292
0x18004a3f4  mov     [r15], r11w
0x18004a3f8  jmp     loc_18004A292
0x18004a3fd  cmp     [rbp+0F0h+var_98], r13d
0x18004a401  jle     short loc_18004A413
0x18004a403  mov     rcx, [rbp+0F0h+var_A0]; hMem
0x18004a407  call    cs:__imp_GlobalFree
0x18004a40e  nop     dword ptr [rax+rax+00h]
0x18004a413  lea     rax, [rbp+0F0h+FeatureBuf]
0x18004a417  mov     [rbp+0F0h+var_98], r13d
0x18004a41b  mov     [rbp+0F0h+var_A0], rax
0x18004a41f  jmp     loc_18004A1DC
0x18004a424  cmp     [rbp+0F0h+var_98], r13d
0x18004a428  jle     short loc_18004A43A
0x18004a42a  mov     rcx, [rbp+0F0h+var_A0]; hMem
0x18004a42e  call    cs:__imp_GlobalFree
0x18004a435  nop     dword ptr [rax+rax+00h]
0x18004a43a  xor     r11d, r11d
0x18004a43d  jmp     loc_18004A26A
0x18004a442  lea     r9, aMsiDbgInvalidD_1; "MSI_DBG: Invalid descriptor format - un"...
0x18004a449  jmp     loc_18004A309
0x18004a44e  cmp     cs:?g_dmDiagnosticMode@@3HA, r11d; int g_dmDiagnosticMode
0x18004a455  jz      loc_18004A1DC
0x18004a45b  lea     r9, aMsiDbgInvalidF; "MSI_DBG: Invalid feature name provided "...
0x18004a462  jmp     loc_18004A309
0x18004a467  cmp     [rsp+1F0h+var_18F], r11b
0x18004a46c  jz      loc_18004A26A
0x18004a472  xor     r9d, r9d; lpParentBuf
0x18004a475  mov     r8, r10; lpFeatureBuf
0x18004a478  xor     edx, edx; iFeatureIndex
0x18004a47a  mov     rcx, rbx; szProduct
0x18004a47d  call    MsiEnumFeaturesW
0x18004a482  xor     ecx, ecx
0x18004a484  test    eax, eax
0x18004a486  jz      short loc_18004A4A9
0x18004a488  cmp     cs:?g_dmDiagnosticMode@@3HA, ecx; int g_dmDiagnosticMode
0x18004a48e  jz      loc_18004A1DC
0x18004a494  mov     [rsp+1F0h+var_198], rcx
0x18004a499  lea     r9, aMsiDbgDescript; "MSI_DBG: Descriptor feature validation "...
0x18004a4a0  mov     [rsp+1F0h+var_1A0], ecx
0x18004a4a4  jmp     loc_18004A313
0x18004a4a9  xor     r9d, r9d; lpParentBuf
0x18004a4ac  mov     [rbp+0F0h+var_98], r13d
0x18004a4b0  lea     rax, [rbp+0F0h+FeatureBuf]
0x18004a4b4  mov     rcx, rbx; szProduct
0x18004a4b7  lea     r8, [rbp+0F0h+FeatureBuf]; lpFeatureBuf
0x18004a4bb  mov     [rbp+0F0h+var_A0], rax
0x18004a4bf  lea     edx, [r9+1]; iFeatureIndex
0x18004a4c3  call    MsiEnumFeaturesW
0x18004a4c8  cmp     eax, 103h
0x18004a4cd  jz      loc_18004A424
0x18004a4d3  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18004a4da  jz      loc_18004A3FD
0x18004a4e0  lea     rax, aNull; "(NULL)"
0x18004a4e7  xor     edx, edx; unsigned __int16
0x18004a4e9  mov     [rsp+1F0h+var_198], rdx; void *
0x18004a4ee  lea     r9, aMsiDbgDescript; "MSI_DBG: Descriptor feature validation "...
0x18004a4f5  mov     [rsp+1F0h+var_1A0], edx; unsigned int
0x18004a4f9  xor     r8d, r8d; int
0x18004a4fc  mov     [rsp+1F0h+var_1A8], rax; unsigned __int16 *
0x18004a501  mov     [rsp+1F0h+var_1B0], rax; unsigned __int16 *
0x18004a506  lea     ecx, [rdx+0Ah]; int
0x18004a509  mov     [rsp+1F0h+var_1B8], rax; unsigned __int16 *
0x18004a50e  mov     [rsp+1F0h+var_1C0], rax; unsigned __int16 *
0x18004a513  mov     [rsp+1F0h+var_1C8], rax; unsigned __int16 *
0x18004a518  mov     [rsp+1F0h+var_1D0], rax; unsigned __int16 *
0x18004a51d  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004a522  jmp     loc_18004A3FD
```
