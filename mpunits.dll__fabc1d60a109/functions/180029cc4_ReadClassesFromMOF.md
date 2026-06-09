# ReadClassesFromMOF

- ea: `0x180029cc4`
- end: `0x180029f42`
- name: `ReadClassesFromMOF`
- size: `638`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18002a5d0`
- `0x18002a9c0`

## callees

- `0x180029cc4`
- `0x180029f50`
- `0x180044842`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x180029d13`
- `msvcrt!malloc` at `0x180029d13`
- `msvcrt!free` at `0x180029e61`
- `msvcrt!free` at `0x180029e9e`
- `msvcrt!free` at `0x180029f1f`
- `msvcrt!free` at `0x180029e61`
- `msvcrt!free` at `0x180029e9e`
- `msvcrt!free` at `0x180029f1f`
- `mimofcodec!MI_Application_NewDeserializer_Mof` at `0x180029dab`
- `mimofcodec!MI_Application_NewDeserializer_Mof` at `0x180029dab`
- `mi!MI_Application_InitializeV1` at `0x180029d53`
- `mi!MI_Application_InitializeV1` at `0x180029d53`
- `mi!mi_clientFT_V1` at `0x180029eb9`

## pseudocode

```c
__int64 __fastcall ReadClassesFromMOF(wchar_t *FileName, char **a2, MI_Instance *a3)
{
  char *v5; // rax
  char *v6; // rsi
  __int64 result; // rax
  MI_Result v8; // ebx
  __int64 v9; // rax
  _QWORD *v10; // r15
  MI_Result v11; // eax
  __int64 v12; // rdx
  void *v13; // r12
  const MI_DeserializerFT *deserializerFT; // rax
  void (__fastcall **v15)(__int64); // rax
  void (__fastcall **v16)(__int64); // rax
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  _OWORD *v18; // [rsp+78h] [rbp-88h] BYREF
  const MI_InstanceFT *v19; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[16]; // [rsp+90h] [rbp-70h] BYREF
  const MI_InstanceFT **v21; // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v22)(MI_Instance **, wchar_t *, _QWORD *, _DWORD *); // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v23)(); // [rsp+B0h] [rbp-50h]
  MI_Instance *extendedError; // [rsp+160h] [rbp+60h] BYREF
  int v25; // [rsp+168h] [rbp+68h] BYREF

  extendedError = a3;
  Block = 0;
  v25 = 0;
  v19 = 0;
  v18 = 0;
  v5 = (char *)malloc(0x50u);
  v6 = v5;
  if ( !v5 )
    return 27;
  memset_0(v5, 0, 0x50u);
  memset_0(v20, 0, 0x78u);
  v8 = MI_Application_InitializeV1(0, 0, 0, (MI_Application *)(v6 + 16));
  if ( v8 )
    goto LABEL_31;
  if ( v6 == (char *)-16LL || (v9 = *((_QWORD *)v6 + 4)) == 0 )
  {
    if ( v6 != (char *)-40LL )
    {
      *(_OWORD *)(v6 + 40) = 0;
      *((_QWORD *)v6 + 7) = 0;
    }
    v8 = MI_RESULT_INVALID_PARAMETER;
  }
  else
  {
    v8 = (*(unsigned int (__fastcall **)(char *, _QWORD, char *))(v9 + 40))(v6 + 16, 0, v6 + 40);
    if ( v8 == MI_RESULT_OK )
    {
      v10 = v6 + 64;
      v8 = (unsigned int)MI_Application_NewDeserializer_Mof(v6 + 16, 0, L"MI_MOF_CIMV2_EXTV1", v6 + 64);
      if ( v8 == MI_RESULT_OK )
      {
        v11 = (unsigned int)ReadFileBuffer(&extendedError, FileName, &Block, &v25);
        v12 = 0;
        v8 = v11;
        if ( v11 == MI_RESULT_OK )
        {
          v13 = Block;
          v21 = &v19;
          v22 = ReadFileBuffer;
          v23 = FreeFileBuffer;
          if ( *v10 == 0xFFEEDDCCFFEEDDCCuLL )
          {
            v8 = (*(unsigned int (__fastcall **)(char *, _QWORD, char *, _BYTE *, void *, int, _QWORD, _QWORD, _QWORD, _QWORD, _OWORD **, MI_Instance *))(*((_QWORD *)v6 + 9) + 48LL))(
                   v6 + 64,
                   0,
                   v6 + 40,
                   v20,
                   Block,
                   v25,
                   0,
                   0,
                   0,
                   0,
                   &v18,
                   extendedError);
            if ( v8 == MI_RESULT_OK )
            {
              free(v13);
              result = 0;
              *(_OWORD *)v6 = *v18;
              *a2 = v6;
              return result;
            }
          }
          else
          {
            if ( extendedError )
              extendedError->ft = 0;
            v8 = MI_RESULT_INVALID_PARAMETER;
          }
          if ( v19 )
            extendedError->ft = v19;
          free(v13);
        }
        if ( *v10 == 0xFFEEDDCCFFEEDDCCuLL )
          deserializerFT = (const MI_DeserializerFT *)*((_QWORD *)v6 + 9);
        else
          deserializerFT = mi_clientFT_V1->deserializerFT;
        ((void (__fastcall *)(char *, __int64, unsigned __int64))deserializerFT->Close)(
          v6 + 64,
          v12,
          0xFFEEDDCCFFEEDDCCuLL);
      }
      if ( v6 != (char *)-40LL )
      {
        v15 = (void (__fastcall **)(__int64))*((_QWORD *)v6 + 7);
        if ( v15 )
          (*v15)((__int64)(v6 + 40));
      }
      goto LABEL_29;
    }
  }
  if ( v6 != (char *)-16LL )
  {
LABEL_29:
    v16 = (void (__fastcall **)(__int64))*((_QWORD *)v6 + 4);
    if ( v16 )
      (*v16)((__int64)(v6 + 16));
  }
LABEL_31:
  free(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180029cc4  mov     [rsp-8+arg_0], rbx
0x180029cc9  mov     [rsp-8+extendedError], r8
0x180029cce  push    rbp
0x180029ccf  push    rsi
0x180029cd0  push    rdi
0x180029cd1  push    r12
0x180029cd3  push    r13
0x180029cd5  push    r14
0x180029cd7  push    r15
0x180029cd9  lea     rbp, [rsp-10h]
0x180029cde  sub     rsp, 110h
0x180029ce5  mov     r12, rcx
0x180029ce8  mov     [rsp+140h+Block], 0
0x180029cf1  mov     ebx, 50h ; 'P'
0x180029cf6  mov     [rbp+40h+arg_18], 0
0x180029cfd  mov     ecx, ebx; Size
0x180029cff  mov     [rbp+40h+var_C0], 0
0x180029d07  mov     r13, rdx
0x180029d0a  mov     [rsp+140h+var_C8], 0
0x180029d13  call    cs:__imp_malloc
0x180029d19  mov     rsi, rax
0x180029d1c  test    rax, rax
0x180029d1f  jnz     short loc_180029D29
0x180029d21  lea     eax, [rbx-35h]
0x180029d24  jmp     loc_180029F27
0x180029d29  mov     r8, rbx; Size
0x180029d2c  xor     edx, edx; Val
0x180029d2e  mov     rcx, rsi; void *
0x180029d31  call    memset_0
0x180029d36  xor     edx, edx; Val
0x180029d38  lea     rcx, [rbp+40h+var_B0]; void *
0x180029d3c  lea     r8d, [rdx+78h]; Size
0x180029d40  call    memset_0
0x180029d45  lea     r14, [rsi+10h]
0x180029d49  xor     r8d, r8d; extendedError
0x180029d4c  mov     r9, r14; application
0x180029d4f  xor     edx, edx; applicationID
0x180029d51  xor     ecx, ecx; flags
0x180029d53  call    cs:__imp_MI_Application_InitializeV1
0x180029d59  mov     ebx, eax
0x180029d5b  test    eax, eax
0x180029d5d  jnz     loc_180029F1C
0x180029d63  lea     rdi, [rsi+28h]
0x180029d67  test    r14, r14
0x180029d6a  jz      loc_180029EED
0x180029d70  mov     rax, [r14+10h]
0x180029d74  test    rax, rax
0x180029d77  jz      loc_180029EED
0x180029d7d  mov     rax, [rax+28h]
0x180029d81  mov     r8, rdi
0x180029d84  xor     edx, edx
0x180029d86  mov     rcx, r14
0x180029d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d8e  mov     ebx, eax
0x180029d90  test    eax, eax
0x180029d92  jnz     loc_180029F03
0x180029d98  lea     r15, [rsi+40h]
0x180029d9c  xor     edx, edx
0x180029d9e  mov     r9, r15
0x180029da1  lea     r8, aMiMofCimv2Extv; "MI_MOF_CIMV2_EXTV1"
0x180029da8  mov     rcx, r14
0x180029dab  call    cs:__imp_MI_Application_NewDeserializer_Mof
0x180029db1  mov     ebx, eax
0x180029db3  test    eax, eax
0x180029db5  jnz     loc_180029ED2
0x180029dbb  lea     r9, [rbp+40h+arg_18]
0x180029dbf  mov     rdx, r12; FileName
0x180029dc2  lea     r8, [rsp+140h+Block]
0x180029dc7  lea     rcx, [rbp+40h+extendedError]; extendedError
0x180029dcb  call    ReadFileBuffer
0x180029dd0  xor     edx, edx
0x180029dd2  mov     ebx, eax
0x180029dd4  mov     r8, 0FFEEDDCCFFEEDDCCh
0x180029dde  test    eax, eax
0x180029de0  jnz     loc_180029EAE
0x180029de6  mov     rcx, [rbp+40h+extendedError]
0x180029dea  lea     rax, [rbp+40h+var_C0]
0x180029dee  mov     r12, [rsp+140h+Block]
0x180029df3  mov     [rbp+40h+var_A0], rax
0x180029df7  lea     rax, ReadFileBuffer
0x180029dfe  mov     [rbp+40h+var_98], rax
0x180029e02  lea     rax, FreeFileBuffer
0x180029e09  mov     [rbp+40h+var_90], rax
0x180029e0d  cmp     [r15], r8
0x180029e10  jnz     short loc_180029E7E
0x180029e12  mov     rax, [r15+8]
0x180029e16  lea     r9, [rbp+40h+var_B0]
0x180029e1a  mov     [rsp+140h+var_E8], rcx
0x180029e1f  mov     r8, rdi
0x180029e22  lea     rcx, [rsp+140h+var_C8]
0x180029e27  mov     [rsp+140h+var_F0], rcx
0x180029e2c  mov     ecx, [rbp+40h+arg_18]
0x180029e2f  mov     rax, [rax+30h]
0x180029e33  mov     [rsp+140h+var_F8], rdx
0x180029e38  mov     [rsp+140h+var_100], rdx
0x180029e3d  mov     [rsp+140h+var_108], rdx
0x180029e42  mov     [rsp+140h+var_110], rdx
0x180029e47  mov     [rsp+140h+var_118], ecx
0x180029e4b  mov     rcx, r15
0x180029e4e  mov     [rsp+140h+var_120], r12
0x180029e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e58  mov     ebx, eax
0x180029e5a  test    eax, eax
0x180029e5c  jnz     short loc_180029E8B
0x180029e5e  mov     rcx, r12; Block
0x180029e61  call    cs:__imp_free
0x180029e67  mov     rax, [rsp+140h+var_C8]
0x180029e6c  movups  xmm0, xmmword ptr [rax]
0x180029e6f  xor     eax, eax
0x180029e71  movdqu  xmmword ptr [rsi], xmm0
0x180029e75  mov     [r13+0], rsi
0x180029e79  jmp     loc_180029F27
0x180029e7e  test    rcx, rcx
0x180029e81  jz      short loc_180029E86
0x180029e83  mov     [rcx], rdx
0x180029e86  mov     ebx, 4
0x180029e8b  mov     rcx, [rbp+40h+var_C0]
0x180029e8f  test    rcx, rcx
0x180029e92  jz      short loc_180029E9B
0x180029e94  mov     rax, [rbp+40h+extendedError]
0x180029e98  mov     [rax], rcx
0x180029e9b  mov     rcx, r12; Block
0x180029e9e  call    cs:__imp_free
0x180029ea4  mov     r8, 0FFEEDDCCFFEEDDCCh
0x180029eae  cmp     [r15], r8
0x180029eb1  jnz     short loc_180029EB9
0x180029eb3  mov     rax, [r15+8]
0x180029eb7  jmp     short loc_180029EC7
0x180029eb9  mov     rax, cs:__imp_mi_clientFT_V1
0x180029ec0  mov     rcx, [rax]
0x180029ec3  mov     rax, [rcx+28h]
0x180029ec7  mov     rax, [rax]
0x180029eca  mov     rcx, r15
0x180029ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ed2  test    rdi, rdi
0x180029ed5  jz      short loc_180029F08
0x180029ed7  mov     rax, [rdi+10h]
0x180029edb  test    rax, rax
0x180029ede  jz      short loc_180029F08
0x180029ee0  mov     rax, [rax]
0x180029ee3  mov     rcx, rdi
0x180029ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029eeb  jmp     short loc_180029F08
0x180029eed  test    rdi, rdi
0x180029ef0  jz      short loc_180029EFE
0x180029ef2  xorps   xmm0, xmm0
0x180029ef5  xor     eax, eax
0x180029ef7  movups  xmmword ptr [rdi], xmm0
0x180029efa  mov     [rdi+10h], rax
0x180029efe  mov     ebx, 4
0x180029f03  test    r14, r14
0x180029f06  jz      short loc_180029F1C
0x180029f08  mov     rax, [r14+10h]
0x180029f0c  test    rax, rax
0x180029f0f  jz      short loc_180029F1C
0x180029f11  mov     rax, [rax]
0x180029f14  mov     rcx, r14
0x180029f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f1c  mov     rcx, rsi; Block
0x180029f1f  call    cs:__imp_free
0x180029f25  mov     eax, ebx
0x180029f27  mov     rbx, [rsp+140h+arg_0]
0x180029f2f  add     rsp, 110h
0x180029f36  pop     r15
0x180029f38  pop     r14
0x180029f3a  pop     r13
0x180029f3c  pop     r12
0x180029f3e  pop     rdi
0x180029f3f  pop     rsi
0x180029f40  pop     rbp
0x180029f41  retn
```
