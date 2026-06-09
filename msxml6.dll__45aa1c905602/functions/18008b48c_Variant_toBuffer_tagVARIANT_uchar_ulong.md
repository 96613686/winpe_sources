# Variant::toBuffer(tagVARIANT,uchar * *,ulong *)

- ea: `0x18008b48c`
- end: `0x18008b611`
- name: `?toBuffer@Variant@@SAJUtagVARIANT@@PEAPEAEPEAK@Z`
- size: `389`
- prototype: `HRESULT __fastcall(tagVARIANT varVariant, unsigned __int8 **pData, unsigned int *pcb)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18008e144`

## callees

- `0x18000fc60`
- `0x18008b48c`
- `0x18008b82c`
- `0x180150ac8`
- `0x18017c1d8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18008b5d6`
- `OLEAUT32!__imp_SysFreeString` at `0x18008b5d6`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008b4e5`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18008b4e5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008b54b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18008b54b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008b529`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18008b529`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008b507`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18008b507`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008b5ef`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18008b5ef`

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
      goto $CleanUp_91;
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
              goto $CleanUp_91;
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
$CleanUp_91:
  if ( pb )
    SafeArrayUnaccessData(parray);
  *pcb = v4;
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x18008b48c  push    rbp
0x18008b48e  push    rbx
0x18008b48f  push    rsi
0x18008b490  push    rdi
0x18008b491  push    r12
0x18008b493  push    r14
0x18008b495  push    r15
0x18008b497  mov     rbp, rsp
0x18008b49a  sub     rsp, 40h
0x18008b49e  movzx   eax, word ptr [varVariant]
0x18008b4a1  xor     edi, edi
0x18008b4a3  test    al, 11h
0x18008b4a5  mov     [pData], rdi
0x18008b4a8  mov     r15, pData
0x18008b4ab  mov     [rbp+pb], 0
0x18008b4b3  mov     r12, pcb
0x18008b4b6  mov     [rbp+lUBound], 0
0x18008b4bd  setnz   r8b
0x18008b4c1  mov     [rbp+lLBound], 0
0x18008b4c8  lea     edx, [rdi+0Dh]
0x18008b4cb  mov     [rbp+cb], edi
0x18008b4ce  bt      ax, dx
0x18008b4d2  setb    al
0x18008b4d5  test    al, r8b
0x18008b4d8  jz      loc_18008B599
0x18008b4de  mov     rsi, [varVariant+8]
0x18008b4e2  mov     varVariant, rsi; psa
0x18008b4e5  call    cs:__imp_SafeArrayGetDim
0x18008b4ec  nop     dword ptr [rax+rax+00h]
0x18008b4f1  cmp     eax, 1
0x18008b4f4  jz      short loc_18008B500
0x18008b4f6  mov     ebx, 80004005h
0x18008b4fb  jmp     $CleanUp_91
0x18008b500  lea     pData, [rbp+pb]; ppvData
0x18008b504  mov     varVariant, rsi; psa
0x18008b507  call    cs:__imp_SafeArrayAccessData
0x18008b50e  nop     dword ptr [rax+rax+00h]
0x18008b513  mov     ebx, eax
0x18008b515  test    eax, eax
0x18008b517  js      $CleanUp_91
0x18008b51d  lea     pcb, [rbp+lLBound]; plLbound
0x18008b521  mov     edx, 1; nDim
0x18008b526  mov     varVariant, rsi; psa
0x18008b529  call    cs:__imp_SafeArrayGetLBound
0x18008b530  nop     dword ptr [rax+rax+00h]
0x18008b535  mov     ebx, eax
0x18008b537  test    eax, eax
0x18008b539  js      $CleanUp_91
0x18008b53f  lea     pcb, [rbp+lUBound]; plUbound
0x18008b543  mov     edx, 1; nDim
0x18008b548  mov     varVariant, rsi; psa
0x18008b54b  call    cs:__imp_SafeArrayGetUBound
0x18008b552  nop     dword ptr [rax+rax+00h]
0x18008b557  mov     ebx, eax
0x18008b559  test    eax, eax
0x18008b55b  js      $CleanUp_91
0x18008b561  mov     edi, [rbp+lUBound]
0x18008b564  sub     edi, [rbp+lLBound]
0x18008b567  add     edi, 1
0x18008b56a  jz      short loc_18008B595
0x18008b56c  mov     ecx, edi; cch
0x18008b56e  mov     ebx, edi
0x18008b570  call    ??$new_array_ne@E@@YAPEAE_J@Z; new_array_ne<uchar>(__int64)
0x18008b575  mov     [r15], rax
0x18008b578  test    rax, rax
0x18008b57b  jnz     short loc_18008B586
0x18008b57d  xor     edi, edi
0x18008b57f  mov     ebx, 8007000Eh
0x18008b584  jmp     short $CleanUp_91
0x18008b586  mov     pData, [rbp+pb]; Src
0x18008b58a  mov     pcb, rbx; Size
0x18008b58d  mov     varVariant, rax; void *
0x18008b590  call    memcpy_0
0x18008b595  xor     ebx, ebx
0x18008b597  jmp     short $CleanUp_91
0x18008b599  movaps  xmm0, xmmword ptr [varVariant]
0x18008b59c  mov     ebx, 1
0x18008b5a1  movsd   xmm1, qword ptr [varVariant+10h]
0x18008b5a6  xor     esi, esi
0x18008b5a8  lea     varVariant, [rbp+var_20]
0x18008b5ac  movaps  [rbp+var_20], xmm0
0x18008b5b0  movsd   [rbp+var_10], xmm1
0x18008b5b5  call    ?toBSTR@Variant@@SAPEAGUtagVARIANT@@@Z; Variant::toBSTR(tagVARIANT)
0x18008b5ba  mov     r14, rax
0x18008b5bd  test    rax, rax
0x18008b5c0  jz      short $CleanUp_91
0x18008b5c2  lea     pcb, [rbp+cb]; pcbUTF8
0x18008b5c6  mov     pData, r15; psz
0x18008b5c9  mov     varVariant, rax; bstr
0x18008b5cc  call    ?BSTRToUTF8@@YAJPEAGPEAPEAEPEAK@Z; BSTRToUTF8(ushort *,uchar * *,ulong *)
0x18008b5d1  mov     varVariant, r14; bstrString
0x18008b5d4  mov     ebx, eax
0x18008b5d6  call    cs:__imp_SysFreeString
0x18008b5dd  nop     dword ptr [rax+rax+00h]
0x18008b5e2  mov     edi, [rbp+cb]
0x18008b5e5  cmp     [rbp+pb], 0
0x18008b5ea  jz      short loc_18008B5FB
0x18008b5ec  mov     varVariant, rsi; psa
0x18008b5ef  call    cs:__imp_SafeArrayUnaccessData
0x18008b5f6  nop     dword ptr [rax+rax+00h]
0x18008b5fb  mov     [r12], edi
0x18008b5ff  mov     eax, ebx
0x18008b601  add     rsp, 40h
0x18008b605  pop     r15
0x18008b607  pop     r14
0x18008b609  pop     r12
0x18008b60b  pop     rdi
0x18008b60c  pop     rsi
0x18008b60d  pop     rbx
0x18008b60e  pop     rbp
0x18008b60f  retn
```
