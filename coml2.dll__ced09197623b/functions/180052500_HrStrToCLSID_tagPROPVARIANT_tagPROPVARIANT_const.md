# HrStrToCLSID(tagPROPVARIANT *,tagPROPVARIANT const *)

- ea: `0x180052500`
- end: `0x1800525d1`
- name: `?HrStrToCLSID@@YAJPEAUtagPROPVARIANT@@PEBU1@@Z`
- size: `209`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180050e60`
- `0x1800514a0`
- `0x180051638`

## callees

- `0x180042800`
- `0x180050c14`
- `0x180052500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005257a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005257a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800525af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800525af`

## pseudocode

```c
__int64 __fastcall HrStrToCLSID(struct tagPROPVARIANT *a1, const struct tagPROPVARIANT *a2)
{
  OLECHAR *bstrVal; // rdi
  int vt; // edx
  int v5; // esi
  int v7; // edx
  int v8; // edx
  unsigned int v9; // ebx
  GUID *v10; // rax
  unsigned __int16 *v12; // [rsp+20h] [rbp-38h] BYREF
  GUID pclsid; // [rsp+28h] [rbp-30h] BYREF

  bstrVal = 0;
  vt = a2->vt;
  v5 = 0;
  v12 = 0;
  pclsid = 0;
  v7 = vt - 8;
  if ( !v7 )
  {
LABEL_4:
    bstrVal = a2->bstrVal;
    goto LABEL_5;
  }
  v8 = v7 - 22;
  if ( v8 )
  {
    if ( v8 != 1 )
      goto LABEL_6;
    goto LABEL_4;
  }
  v9 = HrAStrToWStr(a2->pszVal, &v12);
  if ( v9 )
    return v9;
  bstrVal = v12;
  v5 = 1;
LABEL_5:
  if ( bstrVal )
  {
    v9 = CLSIDFromString(bstrVal, &pclsid);
    if ( !v9 )
    {
      v10 = (GUID *)CoTaskMemAlloc(0x10u);
      if ( v10 )
      {
        *v10 = pclsid;
        a1->hVal.QuadPart = (LONGLONG)v10;
      }
      else
      {
        v9 = -2147024882;
      }
    }
    goto LABEL_13;
  }
LABEL_6:
  v9 = -2147024809;
LABEL_13:
  if ( v5 )
    CoTaskMemFree(bstrVal);
  return v9;
}

```

## disassembly

```asm
0x180052500  mov     [rsp+arg_10], rbx
0x180052505  push    rbp
0x180052506  push    rsi
0x180052507  push    rdi
0x180052508  sub     rsp, 40h
0x18005250c  mov     rax, cs:__security_cookie
0x180052513  xor     rax, rsp
0x180052516  mov     [rsp+58h+var_20], rax
0x18005251b  mov     r8, rdx
0x18005251e  xor     edi, edi
0x180052520  movzx   edx, word ptr [rdx]
0x180052523  xor     esi, esi
0x180052525  mov     [rsp+58h+var_38], rdi
0x18005252a  xorps   xmm0, xmm0
0x18005252d  mov     rbp, rcx
0x180052530  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x180052535  sub     edx, 8
0x180052538  jz      short loc_180052544
0x18005253a  sub     edx, 16h
0x18005253d  jz      short loc_180052554
0x18005253f  cmp     edx, 1
0x180052542  jnz     short loc_18005254D
0x180052544  mov     rdi, [r8+8]
0x180052548  test    rdi, rdi
0x18005254b  jnz     short loc_180052572
0x18005254d  mov     ebx, 80070057h
0x180052552  jmp     short loc_1800525A8
0x180052554  mov     rcx, [r8+8]; lpMultiByteStr
0x180052558  lea     rdx, [rsp+58h+var_38]; unsigned __int16 **
0x18005255d  call    ?HrAStrToWStr@@YAJPEBDPEAPEAG@Z; HrAStrToWStr(char const *,ushort * *)
0x180052562  mov     ebx, eax
0x180052564  test    eax, eax
0x180052566  jnz     short loc_1800525B5
0x180052568  mov     rdi, [rsp+58h+var_38]
0x18005256d  lea     esi, [rax+1]
0x180052570  jmp     short loc_180052548
0x180052572  lea     rdx, [rsp+58h+pclsid]; pclsid
0x180052577  mov     rcx, rdi; lpsz
0x18005257a  call    cs:__imp_CLSIDFromString
0x180052580  mov     ebx, eax
0x180052582  test    eax, eax
0x180052584  jnz     short loc_1800525A8
0x180052586  lea     ecx, [rax+10h]; cb
0x180052589  call    cs:__imp_CoTaskMemAlloc
0x18005258f  test    rax, rax
0x180052592  jnz     short loc_18005259B
0x180052594  mov     ebx, 8007000Eh
0x180052599  jmp     short loc_1800525A8
0x18005259b  movups  xmm0, xmmword ptr [rsp+58h+pclsid.Data1]
0x1800525a0  movdqu  xmmword ptr [rax], xmm0
0x1800525a4  mov     [rbp+8], rax
0x1800525a8  test    esi, esi
0x1800525aa  jz      short loc_1800525B5
0x1800525ac  mov     rcx, rdi; pv
0x1800525af  call    cs:__imp_CoTaskMemFree
0x1800525b5  mov     eax, ebx
0x1800525b7  mov     rcx, [rsp+58h+var_20]
0x1800525bc  xor     rcx, rsp; StackCookie
0x1800525bf  call    __security_check_cookie
0x1800525c4  mov     rbx, [rsp+58h+arg_10]
0x1800525c9  add     rsp, 40h
0x1800525cd  pop     rdi
0x1800525ce  pop     rsi
0x1800525cf  pop     rbp
0x1800525d0  retn
```
