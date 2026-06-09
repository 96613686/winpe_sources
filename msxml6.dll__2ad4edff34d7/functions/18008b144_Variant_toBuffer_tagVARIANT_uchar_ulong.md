# Variant::toBuffer(tagVARIANT,uchar * *,ulong *)

- ea: `0x18008b144`
- end: `0x18008b2a0`
- name: `?toBuffer@Variant@@SAJUtagVARIANT@@PEAPEAEPEAK@Z`
- size: `348`
- prototype: `__int64 __fastcall(tagVARIANT *varVariant, unsigned __int8 **pData, unsigned int *pcb)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18008dd9c`

## callees

- `0x180035d58`
- `0x18008b144`
- `0x18008b4a8`
- `0x18014d784`
- `0x180178528`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18008b272`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b272`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008b19d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008b19d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008b1f1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008b1f1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008b1d5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008b1d5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008b1b9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008b1b9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008b285`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008b285`

## pseudocode

```c
__int64 __fastcall Variant::toBuffer(tagVARIANT *varVariant, unsigned __int8 **pData, unsigned int *pcb)
{
  unsigned __int16 vt; // ax
  unsigned int v4; // edi
  SAFEARRAY *parray; // rsi
  HRESULT LBound; // ebx
  unsigned __int8 *v9; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  wchar_t *v11; // rax
  wchar_t *v12; // r14
  tagVARIANT v14; // [rsp+20h] [rbp-20h] BYREF
  int lUBound; // [rsp+80h] [rbp+40h] BYREF
  int lLBound; // [rsp+88h] [rbp+48h] BYREF
  unsigned int cb; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int8 *pb; // [rsp+98h] [rbp+58h] BYREF

  vt = varVariant->vt;
  v4 = 0;
  *pData = 0;
  pb = 0;
  lUBound = 0;
  lLBound = 0;
  cb = 0;
  if ( (vt & 0x11) != 0 && (vt & 0x2000) != 0 )
  {
    parray = varVariant->parray;
    if ( SafeArrayGetDim(parray) != 1 )
    {
      LBound = -2147467259;
      goto $CleanUp_93;
    }
    LBound = SafeArrayAccessData(parray, (void **)&pb);
    if ( LBound >= 0 )
    {
      LBound = SafeArrayGetLBound(parray, 1u, &lLBound);
      if ( LBound >= 0 )
      {
        LBound = SafeArrayGetUBound(parray, 1u, &lUBound);
        if ( LBound >= 0 )
        {
          v4 = lUBound - lLBound + 1;
          if ( lUBound - lLBound != -1 )
          {
            v9 = (unsigned __int8 *)new_array_ne<unsigned char>(v4);
            *pData = v9;
            if ( !v9 )
            {
              v4 = 0;
              LBound = -2147024882;
              goto $CleanUp_93;
            }
            memcpy_0(v9, pb, v4);
          }
          LBound = 0;
        }
      }
    }
  }
  else
  {
    LBound = 1;
    pRecInfo = varVariant->pRecInfo;
    parray = 0;
    v14.0 = varVariant->0;
    v14.pRecInfo = pRecInfo;
    v11 = Variant::toBSTR(&v14);
    v12 = v11;
    if ( v11 )
    {
      LBound = BSTRToUTF8(v11, pData, &cb);
      SysFreeString(v12);
      v4 = cb;
    }
  }
$CleanUp_93:
  if ( pb )
    SafeArrayUnaccessData(parray);
  *pcb = v4;
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x18008b144  push    rbp
0x18008b146  push    rbx
0x18008b147  push    rsi
0x18008b148  push    rdi
0x18008b149  push    r12
0x18008b14b  push    r14
0x18008b14d  push    r15
0x18008b14f  mov     rbp, rsp
0x18008b152  sub     rsp, 40h
0x18008b156  movzx   eax, word ptr [varVariant]
0x18008b159  xor     edi, edi
0x18008b15b  test    al, 11h
0x18008b15d  mov     [pData], rdi
0x18008b160  mov     r15, pData
0x18008b163  mov     [rbp+pb], 0
0x18008b16b  mov     r12, pcb
0x18008b16e  mov     [rbp+lUBound], 0
0x18008b175  setnz   r8b
0x18008b179  mov     [rbp+lLBound], 0
0x18008b180  lea     edx, [rdi+0Dh]
0x18008b183  mov     [rbp+cb], edi
0x18008b186  bt      ax, dx
0x18008b18a  setb    al
0x18008b18d  test    al, r8b
0x18008b190  jz      loc_18008B235
0x18008b196  mov     rsi, [varVariant+8]
0x18008b19a  mov     varVariant, rsi; psa
0x18008b19d  call    cs:__imp_SafeArrayGetDim
0x18008b1a3  cmp     eax, 1
0x18008b1a6  jz      short loc_18008B1B2
0x18008b1a8  mov     ebx, 80004005h
0x18008b1ad  jmp     $CleanUp_93
0x18008b1b2  lea     pData, [rbp+pb]; ppvData
0x18008b1b6  mov     varVariant, rsi; psa
0x18008b1b9  call    cs:__imp_SafeArrayAccessData
0x18008b1bf  mov     ebx, eax
0x18008b1c1  test    eax, eax
0x18008b1c3  js      $CleanUp_93
0x18008b1c9  lea     pcb, [rbp+lLBound]; plLbound
0x18008b1cd  mov     edx, 1; nDim
0x18008b1d2  mov     varVariant, rsi; psa
0x18008b1d5  call    cs:__imp_SafeArrayGetLBound
0x18008b1db  mov     ebx, eax
0x18008b1dd  test    eax, eax
0x18008b1df  js      $CleanUp_93
0x18008b1e5  lea     pcb, [rbp+lUBound]; plUbound
0x18008b1e9  mov     edx, 1; nDim
0x18008b1ee  mov     varVariant, rsi; psa
0x18008b1f1  call    cs:__imp_SafeArrayGetUBound
0x18008b1f7  mov     ebx, eax
0x18008b1f9  test    eax, eax
0x18008b1fb  js      short $CleanUp_93
0x18008b1fd  mov     edi, [rbp+lUBound]
0x18008b200  sub     edi, [rbp+lLBound]
0x18008b203  add     edi, 1
0x18008b206  jz      short loc_18008B231
0x18008b208  mov     ecx, edi; cch
0x18008b20a  mov     ebx, edi
0x18008b20c  call    ??$new_array_ne@E@@YAPEAE_J@Z; new_array_ne<uchar>(__int64)
0x18008b211  mov     [r15], rax
0x18008b214  test    rax, rax
0x18008b217  jnz     short loc_18008B222
0x18008b219  xor     edi, edi
0x18008b21b  mov     ebx, 8007000Eh
0x18008b220  jmp     short $CleanUp_93
0x18008b222  mov     pData, [rbp+pb]; Src
0x18008b226  mov     pcb, rbx; Size
0x18008b229  mov     varVariant, rax; void *
0x18008b22c  call    memcpy_0
0x18008b231  xor     ebx, ebx
0x18008b233  jmp     short $CleanUp_93
0x18008b235  movaps  xmm0, xmmword ptr [varVariant]
0x18008b238  mov     ebx, 1
0x18008b23d  movsd   xmm1, qword ptr [varVariant+10h]
0x18008b242  xor     esi, esi
0x18008b244  lea     varVariant, [rbp+var_20]
0x18008b248  movaps  [rbp+var_20], xmm0
0x18008b24c  movsd   [rbp+var_10], xmm1
0x18008b251  call    ?toBSTR@Variant@@SAPEAGUtagVARIANT@@@Z; Variant::toBSTR(tagVARIANT)
0x18008b256  mov     r14, rax
0x18008b259  test    rax, rax
0x18008b25c  jz      short $CleanUp_93
0x18008b25e  lea     pcb, [rbp+cb]; pcbUTF8
0x18008b262  mov     pData, r15; psz
0x18008b265  mov     varVariant, rax; bstr
0x18008b268  call    ?BSTRToUTF8@@YAJPEAGPEAPEAEPEAK@Z; BSTRToUTF8(ushort *,uchar * *,ulong *)
0x18008b26d  mov     varVariant, r14; bstrString
0x18008b270  mov     ebx, eax
0x18008b272  call    cs:__imp_SysFreeString
0x18008b278  mov     edi, [rbp+cb]
0x18008b27b  cmp     [rbp+pb], 0
0x18008b280  jz      short loc_18008B28B
0x18008b282  mov     varVariant, rsi; psa
0x18008b285  call    cs:__imp_SafeArrayUnaccessData
0x18008b28b  mov     [r12], edi
0x18008b28f  mov     eax, ebx
0x18008b291  add     rsp, 40h
0x18008b295  pop     r15
0x18008b297  pop     r14
0x18008b299  pop     r12
0x18008b29b  pop     rdi
0x18008b29c  pop     rsi
0x18008b29d  pop     rbx
0x18008b29e  pop     rbp
0x18008b29f  retn
```
