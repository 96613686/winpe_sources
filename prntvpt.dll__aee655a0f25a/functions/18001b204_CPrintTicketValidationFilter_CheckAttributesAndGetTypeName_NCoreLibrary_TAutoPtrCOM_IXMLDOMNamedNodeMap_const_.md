# CPrintTicketValidationFilter::CheckAttributesAndGetTypeName(NCoreLibrary::TAutoPtrCOM<IXMLDOMNamedNodeMap> const &,long,IXMLDOMElement *,NCoreLibrary::TAutoPtrBSTR &)

- ea: `0x18001b204`
- end: `0x18001b4a7`
- name: `?CheckAttributesAndGetTypeName@CPrintTicketValidationFilter@@QEAAJAEBV?$TAutoPtrCOM@UIXMLDOMNamedNodeMap@@@NCoreLibrary@@JPEAUIXMLDOMElement@@AEAVTAutoPtrBSTR@3@@Z`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd50`

## callees

- `0x180003318`
- `0x1800056e0`
- `0x180005e70`
- `0x18001b204`
- `0x180022594`
- `0x180023010`

## string_xrefs

- `0x18001b2ed`: `http://www.w3.org/2001/XMLSchema-instance`
- `0x18001b2c2`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c
__int64 __fastcall CPrintTicketValidationFilter::CheckAttributesAndGetTypeName(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // rcx
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rcx
  int v14; // r8d
  int v15; // edx
  int v16; // edx
  int v17; // ecx
  wchar_t *v18; // rbx
  int v19; // eax
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // rdx
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v26; // [rsp+28h] [rbp-40h]
  __int64 v27; // [rsp+30h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+38h] [rbp-30h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-28h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-20h] BYREF
  _QWORD v31[3]; // [rsp+50h] [rbp-18h] BYREF

  v9 = 0;
  v10 = 0;
  if ( a3 > 0 )
  {
    while ( 1 )
    {
      if ( v9 < 0 )
        return (unsigned int)v9;
      v11 = *a2;
      v30 = 0;
      v27 = 0;
      v28 = 0;
      String1 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 80LL))(v11, v10, &v30);
      if ( v9 >= 0 )
      {
        v9 = (**v30)(v30, &IID_IXMLDOMAttribute, &v27);
        if ( v9 >= 0 )
          v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v27 + 312LL))(v27, &v28);
      }
      if ( v9 == 1 || (v12 = v28) == 0 )
      {
        v31[0] = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v27 + 320LL))(v27, v31) < 0 )
        {
          v23 = 0;
          v24 = L"A Value element contains an attribute with no defined namespace.";
        }
        else
        {
          v23 = (const unsigned __int16 *)v31[0];
          v24 = L"A Value element contains an attribute with prefix '%s', which has no defined namespace.";
        }
        v9 = CValidationStatus::SetValidationFailure((CValidationStatus *)(a1 + 8), v24, v23, 0, 0, v26);
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v31);
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String1);
        NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v28);
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v27);
        NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v30);
        return (unsigned int)v9;
      }
      if ( v9 < 0 )
        break;
      v13 = v28;
      do
      {
        v14 = *(const unsigned __int16 *)((char *)v13 + (char *)L"http://www.w3.org/2000/xmlns/" - (char *)v28);
        v15 = *v13 - v14;
        if ( v15 )
          break;
        ++v13;
      }
      while ( v14 );
      if ( v15 )
        break;
LABEL_33:
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&String1);
      NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(&v28);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v27);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v30);
      if ( (int)++v10 >= a3 )
        return (unsigned int)v9;
    }
    do
    {
      v16 = *(const unsigned __int16 *)((char *)v12 + (char *)L"http://www.w3.org/2001/XMLSchema-instance" - (char *)v28);
      v17 = *v12 - v16;
      if ( v17 )
        break;
      ++v12;
    }
    while ( v16 );
    v31[0] = 0;
    if ( v17 )
    {
      if ( (*(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a4 + 272LL))(a4, v31) >= 0 )
      {
        v20 = (const unsigned __int16 *)v31[0];
        if ( v31[0] )
        {
          v21 = 0;
          v22 = L"The value element '%s' contains unexpected attributes. only namespace attributes or type declarations are allowed.";
          goto LABEL_30;
        }
      }
      v22 = L"The value element contains unexpected attributes.";
    }
    else
    {
      if ( v9 < 0 )
        goto LABEL_32;
      v9 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v27 + 328LL))(v27, &String1);
      if ( v9 < 0 )
        goto LABEL_32;
      v18 = String1;
      if ( String1 )
      {
        if ( !wcscmp_0(String1, L"type") )
        {
          v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 208LL))(v27, a5);
LABEL_31:
          v9 = v19;
LABEL_32:
          NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v31);
          goto LABEL_33;
        }
        if ( v18 )
        {
          v20 = v28;
          if ( v28 )
          {
            v21 = v18;
            v22 = L"An unexpected attribute %s:%s exists on a Value element.";
LABEL_30:
            v19 = CValidationStatus::SetValidationFailure((CValidationStatus *)(a1 + 8), v22, v20, v21, 0, v26);
            goto LABEL_31;
          }
        }
      }
      v22 = L"An unexpected attribute exists on a Value element.";
    }
    v21 = 0;
    v20 = 0;
    goto LABEL_30;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001b204  push    rbp
0x18001b206  push    rbx
0x18001b207  push    rsi
0x18001b208  push    rdi
0x18001b209  push    r12
0x18001b20b  push    r13
0x18001b20d  push    r14
0x18001b20f  push    r15
0x18001b211  mov     rbp, rsp
0x18001b214  sub     rsp, 68h
0x18001b218  xor     r13d, r13d
0x18001b21b  mov     r15, r9
0x18001b21e  mov     r14d, r8d
0x18001b221  mov     r12, rdx
0x18001b224  mov     rdi, rcx
0x18001b227  mov     ebx, r13d
0x18001b22a  mov     esi, r13d
0x18001b22d  test    r8d, r8d
0x18001b230  jle     loc_18001B494
0x18001b236  test    ebx, ebx
0x18001b238  js      loc_18001B494
0x18001b23e  mov     rcx, [r12]
0x18001b242  lea     r8, [rbp+var_20]
0x18001b246  mov     [rbp+var_20], r13
0x18001b24a  mov     edx, esi
0x18001b24c  mov     [rbp+var_38], r13
0x18001b250  mov     [rbp+var_30], r13
0x18001b254  mov     [rbp+String1], r13
0x18001b258  mov     rax, [rcx]
0x18001b25b  mov     rax, [rax+50h]
0x18001b25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b264  mov     ebx, eax
0x18001b266  test    eax, eax
0x18001b268  js      short loc_18001B2A3
0x18001b26a  mov     rcx, [rbp+var_20]
0x18001b26e  lea     r8, [rbp+var_38]
0x18001b272  lea     rdx, IID_IXMLDOMAttribute
0x18001b279  mov     rax, [rcx]
0x18001b27c  mov     rax, [rax]
0x18001b27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b284  mov     ebx, eax
0x18001b286  test    eax, eax
0x18001b288  js      short loc_18001B2A3
0x18001b28a  mov     rcx, [rbp+var_38]
0x18001b28e  lea     rdx, [rbp+var_30]
0x18001b292  mov     rax, [rcx]
0x18001b295  mov     rax, [rax+138h]
0x18001b29c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2a1  mov     ebx, eax
0x18001b2a3  cmp     ebx, 1
0x18001b2a6  jz      loc_18001B41E
0x18001b2ac  mov     rax, [rbp+var_30]
0x18001b2b0  test    rax, rax
0x18001b2b3  jz      loc_18001B41E
0x18001b2b9  test    ebx, ebx
0x18001b2bb  js      short loc_18001B2ED
0x18001b2bd  test    rax, rax
0x18001b2c0  jz      short loc_18001B2ED
0x18001b2c2  lea     r9, aHttpWwwW3Org20_2; "http://www.w3.org/2000/xmlns/"
0x18001b2c9  mov     rcx, rax
0x18001b2cc  sub     r9, rax
0x18001b2cf  movzx   edx, word ptr [rcx]
0x18001b2d2  movzx   r8d, word ptr [rcx+r9]
0x18001b2d7  sub     edx, r8d
0x18001b2da  jnz     short loc_18001B2E5
0x18001b2dc  add     rcx, 2
0x18001b2e0  test    r8d, r8d
0x18001b2e3  jnz     short loc_18001B2CF
0x18001b2e5  test    edx, edx
0x18001b2e7  jz      loc_18001B3ED
0x18001b2ed  lea     r8, aHttpWwwW3Org20_3; "http://www.w3.org/2001/XMLSchema-instan"...
0x18001b2f4  sub     r8, rax
0x18001b2f7  movzx   ecx, word ptr [rax]
0x18001b2fa  movzx   edx, word ptr [rax+r8]
0x18001b2ff  sub     ecx, edx
0x18001b301  jnz     short loc_18001B30B
0x18001b303  add     rax, 2
0x18001b307  test    edx, edx
0x18001b309  jnz     short loc_18001B2F7
0x18001b30b  mov     [rbp+var_18], r13
0x18001b30f  test    ecx, ecx
0x18001b311  jnz     loc_18001B398
0x18001b317  test    ebx, ebx
0x18001b319  js      loc_18001B3E4
0x18001b31f  mov     rcx, [rbp+var_38]
0x18001b323  lea     rdx, [rbp+String1]
0x18001b327  mov     rax, [rcx]
0x18001b32a  mov     rax, [rax+148h]
0x18001b331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b336  mov     ebx, eax
0x18001b338  test    eax, eax
0x18001b33a  js      loc_18001B3E4
0x18001b340  mov     rbx, [rbp+String1]
0x18001b344  test    rbx, rbx
0x18001b347  jz      short loc_18001B38F
0x18001b349  lea     rdx, aType; "type"
0x18001b350  mov     rcx, rbx; String1
0x18001b353  call    wcscmp_0
0x18001b358  test    eax, eax
0x18001b35a  jnz     short loc_18001B375
0x18001b35c  mov     rcx, [rbp+var_38]
0x18001b360  mov     rdx, [rbp+arg_20]
0x18001b364  mov     rax, [rcx]
0x18001b367  mov     rax, [rax+0D0h]
0x18001b36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b373  jmp     short loc_18001B3E2
0x18001b375  test    rbx, rbx
0x18001b378  jz      short loc_18001B38F
0x18001b37a  mov     r8, [rbp+var_30]
0x18001b37e  test    r8, r8
0x18001b381  jz      short loc_18001B38F
0x18001b383  mov     r9, rbx
0x18001b386  lea     rdx, aAnUnexpectedAt; "An unexpected attribute %s:%s exists on"...
0x18001b38d  jmp     short loc_18001B3D4
0x18001b38f  lea     rdx, aAnUnexpectedAt_0; "An unexpected attribute exists on a Val"...
0x18001b396  jmp     short loc_18001B3CE
0x18001b398  mov     rax, [r15]
0x18001b39b  lea     rdx, [rbp+var_18]
0x18001b39f  mov     rcx, r15
0x18001b3a2  mov     rax, [rax+110h]
0x18001b3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3ae  test    eax, eax
0x18001b3b0  js      short loc_18001B3C7
0x18001b3b2  mov     r8, [rbp+var_18]
0x18001b3b6  test    r8, r8
0x18001b3b9  jz      short loc_18001B3C7
0x18001b3bb  xor     r9d, r9d
0x18001b3be  lea     rdx, aTheValueElemen; "The value element '%s' contains unexpec"...
0x18001b3c5  jmp     short loc_18001B3D4
0x18001b3c7  lea     rdx, aTheValueElemen_0; "The value element contains unexpected a"...
0x18001b3ce  xor     r9d, r9d; unsigned __int16 *
0x18001b3d1  xor     r8d, r8d; unsigned __int16 *
0x18001b3d4  lea     rcx, [rdi+8]; this
0x18001b3d8  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x18001b3dd  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001b3e2  mov     ebx, eax
0x18001b3e4  lea     rcx, [rbp+var_18]
0x18001b3e8  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b3ed  lea     rcx, [rbp+String1]
0x18001b3f1  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b3f6  lea     rcx, [rbp+var_30]
0x18001b3fa  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b3ff  lea     rcx, [rbp+var_38]
0x18001b403  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b408  lea     rcx, [rbp+var_20]
0x18001b40c  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b411  inc     esi
0x18001b413  cmp     esi, r14d
0x18001b416  jl      loc_18001B236
0x18001b41c  jmp     short loc_18001B494
0x18001b41e  mov     rcx, [rbp+var_38]
0x18001b422  lea     rdx, [rbp+var_18]
0x18001b426  mov     [rbp+var_18], r13
0x18001b42a  mov     rax, [rcx]
0x18001b42d  mov     rax, [rax+140h]
0x18001b434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b439  xor     r9d, r9d; unsigned __int16 *
0x18001b43c  mov     [rsp+68h+var_48], r13; unsigned __int16 *
0x18001b441  lea     rcx, [rdi+8]; this
0x18001b445  test    eax, eax
0x18001b447  js      short loc_18001B456
0x18001b449  mov     r8, [rbp+var_18]
0x18001b44d  lea     rdx, aAValueElementC_0; "A Value element contains an attribute w"...
0x18001b454  jmp     short loc_18001B460
0x18001b456  xor     r8d, r8d; unsigned __int16 *
0x18001b459  lea     rdx, aAValueElementC; "A Value element contains an attribute w"...
0x18001b460  call    ?SetValidationFailure@CValidationStatus@@QEAAJPEBG0000@Z; CValidationStatus::SetValidationFailure(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001b465  lea     rcx, [rbp+var_18]
0x18001b469  mov     ebx, eax
0x18001b46b  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b470  lea     rcx, [rbp+String1]
0x18001b474  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b479  lea     rcx, [rbp+var_30]
0x18001b47d  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001b482  lea     rcx, [rbp+var_38]
0x18001b486  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b48b  lea     rcx, [rbp+var_20]
0x18001b48f  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001b494  mov     eax, ebx
0x18001b496  add     rsp, 68h
0x18001b49a  pop     r15
0x18001b49c  pop     r14
0x18001b49e  pop     r13
0x18001b4a0  pop     r12
0x18001b4a2  pop     rdi
0x18001b4a3  pop     rsi
0x18001b4a4  pop     rbx
0x18001b4a5  pop     rbp
0x18001b4a6  retn
```
