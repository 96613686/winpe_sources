# GetUrlArrayAndInfoFromNextUpdateLocation

- ea: `0x180025b04`
- end: `0x180025c33`
- name: `GetUrlArrayAndInfoFromNextUpdateLocation`
- size: `303`
- prototype: `__int64(unsigned int, __int64, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025a50`

## callees

- `0x1800139c0`
- `0x180015cc0`
- `0x180016c40`
- `0x180016cb0`
- `0x18001acb4`
- `0x180025b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025bb9`

## pseudocode

```c
__int64 GetUrlArrayAndInfoFromNextUpdateLocation(unsigned int a1, __int64 a2, ...)
{
  int v4; // r15d
  int v5; // edx
  unsigned int ArrayInSingleBufferEncodedForm; // ebx
  unsigned int v7; // esi
  __int64 v8; // rdi
  __int64 v9; // r14
  __int64 i; // rbp
  struct _CRYPT_URL_ARRAY **v11; // rdx
  int v13; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v14[80]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+90h] [rbp+18h]
  unsigned int *v17; // [rsp+98h] [rbp+20h]
  __int64 v18; // [rsp+A0h] [rbp+28h]
  __int64 v19; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v15 = va_arg(va1, _QWORD);
  v17 = va_arg(va1, unsigned int *);
  v18 = va_arg(va1, _QWORD);
  v19 = va_arg(va1, _QWORD);
  v13 = 0;
  v4 = 0;
  CCryptUrlArray::CCryptUrlArray((CCryptUrlArray *)v14, a2, v15, &v13);
  ArrayInSingleBufferEncodedForm = v13;
  v7 = 0;
  if ( v13 == 1 )
  {
    do
    {
      if ( v7 >= a1 )
        break;
      v8 = *(_QWORD *)(a2 + 16LL * v7 + 8);
      if ( v8 )
      {
        v9 = *(_QWORD *)(v8 + 8);
        for ( i = 0; (unsigned int)i < *(_DWORD *)v8; i = (unsigned int)(i + 1) )
        {
          if ( ArrayInSingleBufferEncodedForm != 1 )
            break;
          v5 = 3 * i;
          if ( *(_DWORD *)(v9 + 24 * i) == 7 )
          {
            ArrayInSingleBufferEncodedForm = CCryptUrlArray::AddUrl(
                                               (CCryptUrlArray *)v14,
                                               *(unsigned __int16 **)(v9 + 24 * i + 8),
                                               1);
            v4 = 1;
          }
        }
      }
      ++v7;
    }
    while ( ArrayInSingleBufferEncodedForm == 1 );
    if ( !v4 )
    {
      if ( ArrayInSingleBufferEncodedForm != 1 )
        goto LABEL_19;
      SetLastError(0x80092004);
      ArrayInSingleBufferEncodedForm = 0;
    }
    if ( ArrayInSingleBufferEncodedForm == 1 )
    {
      va_copy((va_list)v11, va);
      if ( !v15 )
        v11 = 0;
      ArrayInSingleBufferEncodedForm = CCryptUrlArray::GetArrayInSingleBufferEncodedForm(
                                         (CCryptUrlArray *)v14,
                                         v11,
                                         v17);
      if ( ArrayInSingleBufferEncodedForm == 1 )
      {
        v5 = v19;
        if ( v19 )
          InitializeDefaultUrlInfo(v18);
      }
    }
  }
LABEL_19:
  CCryptUrlArray::FreeArray((CCryptUrlArray *)v14, v5);
  return ArrayInSingleBufferEncodedForm;
}

```

## disassembly

```asm
0x180025b04  mov     rax, rsp
0x180025b07  mov     [rax+8], rbx
0x180025b0b  mov     [rax+20h], r9
0x180025b0f  mov     [rax+18h], r8
0x180025b13  push    rbp
0x180025b14  push    rsi
0x180025b15  push    rdi
0x180025b16  push    r12
0x180025b18  push    r13
0x180025b1a  push    r14
0x180025b1c  push    r15
0x180025b1e  sub     rsp, 40h
0x180025b22  mov     r12d, ecx
0x180025b25  mov     dword ptr [rax-58h], 0
0x180025b2c  lea     rcx, [rax-50h]; this
0x180025b30  mov     r13, rdx
0x180025b33  lea     r9, [rax-58h]; int *
0x180025b37  xor     r15d, r15d
0x180025b3a  call    ??0CCryptUrlArray@@QEAA@KKAEAH@Z; CCryptUrlArray::CCryptUrlArray(ulong,ulong,int &)
0x180025b3f  mov     ebx, [rsp+78h+var_58]
0x180025b43  xor     esi, esi
0x180025b45  cmp     ebx, 1
0x180025b48  jnz     loc_180025C0F
0x180025b4e  cmp     esi, r12d
0x180025b51  jnb     short loc_180025BAA
0x180025b53  mov     eax, esi
0x180025b55  add     rax, rax
0x180025b58  mov     rdi, [r13+rax*8+8]
0x180025b5d  test    rdi, rdi
0x180025b60  jz      short loc_180025BA3
0x180025b62  mov     r14, [rdi+8]
0x180025b66  xor     ebp, ebp
0x180025b68  cmp     [rdi], ebp
0x180025b6a  jbe     short loc_180025BA3
0x180025b6c  cmp     ebx, 1
0x180025b6f  jnz     short loc_180025BA3
0x180025b71  lea     rdx, ds:0[rbp*2]
0x180025b79  add     rdx, rbp
0x180025b7c  cmp     dword ptr [r14+rdx*8], 7
0x180025b81  jnz     short loc_180025B9D
0x180025b83  mov     rdx, [r14+rdx*8+8]; Src
0x180025b88  lea     rcx, [rsp+78h+var_50]; this
0x180025b8d  mov     r8d, ebx; int
0x180025b90  call    ?AddUrl@CCryptUrlArray@@QEAAHPEAGH@Z; CCryptUrlArray::AddUrl(ushort *,int)
0x180025b95  mov     ebx, eax
0x180025b97  mov     r15d, 1
0x180025b9d  inc     ebp
0x180025b9f  cmp     ebp, [rdi]
0x180025ba1  jb      short loc_180025B6C
0x180025ba3  inc     esi
0x180025ba5  cmp     ebx, 1
0x180025ba8  jz      short loc_180025B4E
0x180025baa  test    r15d, r15d
0x180025bad  jnz     short loc_180025BC1
0x180025baf  cmp     ebx, 1
0x180025bb2  jnz     short loc_180025C0F
0x180025bb4  mov     ecx, 80092004h; dwErrCode
0x180025bb9  call    cs:__imp_SetLastError
0x180025bbf  xor     ebx, ebx
0x180025bc1  cmp     ebx, 1
0x180025bc4  jnz     short loc_180025C0F
0x180025bc6  mov     r8, [rsp+78h+arg_18]; unsigned int *
0x180025bce  lea     rdx, [rsp+78h+arg_10]
0x180025bd6  xor     eax, eax
0x180025bd8  lea     rcx, [rsp+78h+var_50]; this
0x180025bdd  cmp     [rsp+78h+arg_10], rax
0x180025be5  cmovz   rdx, rax; struct _CRYPT_URL_ARRAY **
0x180025be9  call    ?GetArrayInSingleBufferEncodedForm@CCryptUrlArray@@QEAAHPEAPEAU_CRYPT_URL_ARRAY@@PEAK@Z; CCryptUrlArray::GetArrayInSingleBufferEncodedForm(_CRYPT_URL_ARRAY * *,ulong *)
0x180025bee  mov     ebx, eax
0x180025bf0  cmp     eax, 1
0x180025bf3  jnz     short loc_180025C0F
0x180025bf5  mov     rdx, [rsp+78h+arg_28]
0x180025bfd  test    rdx, rdx
0x180025c00  jz      short loc_180025C0F
0x180025c02  mov     rcx, [rsp+78h+arg_20]
0x180025c0a  call    InitializeDefaultUrlInfo
0x180025c0f  lea     rcx, [rsp+78h+var_50]; this
0x180025c14  call    ?FreeArray@CCryptUrlArray@@QEAAXH@Z; CCryptUrlArray::FreeArray(int)
0x180025c19  mov     eax, ebx
0x180025c1b  mov     rbx, [rsp+78h+arg_0]
0x180025c23  add     rsp, 40h
0x180025c27  pop     r15
0x180025c29  pop     r14
0x180025c2b  pop     r13
0x180025c2d  pop     r12
0x180025c2f  pop     rdi
0x180025c30  pop     rsi
0x180025c31  pop     rbp
0x180025c32  retn
```
