# AssemblyExclusion::LoadCbsExclusionList(void)

- ea: `0x180001808`
- end: `0x180001c87`
- name: `?LoadCbsExclusionList@AssemblyExclusion@@AEAAJXZ`
- size: `1151`
- prototype: `__int64 __fastcall(AssemblyExclusion *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180012884`

## callees

- `0x180001360`
- `0x180001808`
- `0x180001de0`
- `0x180001e8c`
- `0x1800020f0`
- `0x1800304ec`
- `0x180030568`
- `0x180030d84`
- `0x18003f280`

## import_xrefs

- `mscoree!GetXMLObject` at `0x1800018cb`
- `mscoree!GetXMLObject` at `0x1800018cb`
- `mscoree!CreateConfigStream` at `0x18000198c`
- `mscoree!CreateConfigStream` at `0x18000198c`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall AssemblyExclusion::LoadCbsExclusionList(AssemblyExclusion *this)
{
  int XMLObject; // esi
  int v3; // eax
  void *v4; // rcx
  void *v5; // r14
  bool v6; // cl
  int v7; // eax
  _QWORD *v8; // rbx
  __int64 v10; // [rsp+28h] [rbp-31h] BYREF
  int v11; // [rsp+30h] [rbp-29h]
  __int64 v12; // [rsp+38h] [rbp-21h] BYREF
  int v13; // [rsp+40h] [rbp-19h]
  _QWORD *v14; // [rsp+48h] [rbp-11h]
  int v15; // [rsp+50h] [rbp-9h]
  _DWORD v16[2]; // [rsp+58h] [rbp-1h] BYREF
  int v17; // [rsp+60h] [rbp+7h]
  void *lpMem; // [rsp+68h] [rbp+Fh]
  _DWORD v19[2]; // [rsp+70h] [rbp+17h] BYREF
  int v20; // [rsp+78h] [rbp+1Fh]
  void *v21; // [rsp+80h] [rbp+27h]

  XMLObject = 0;
  v19[0] = 2;
  v19[1] = 2;
  v20 = 16;
  v21 = (void *)&SString::s_EmptyBuffer;
  if ( !AssemblyExclusion::GetHighestVersionedExclusionFile(this, (struct SString *)v19) )
    goto LABEL_79;
  v16[0] = 2;
  v16[1] = 2;
  v17 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  Helpers::GetVersionDirectoryPathFromCurrentModulePath((struct SString *)v16);
  SString::Append((SString *)v16, L"\\");
  SString::Append((SString *)v16, (const struct SString *)v19);
  v13 = 0;
  v10 = 0;
  v11 = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
  XMLObject = GetXMLObject(&v12);
  v3 = v13;
  if ( v12 )
    v3 = 1;
  v13 = v3;
  if ( XMLObject >= 0 )
  {
    v10 = 0;
    SString::ConvertToUnicode((SString *)v16);
    v5 = lpMem;
    v6 = (unsigned int)CreateConfigStream(lpMem, &v10) == -2147024894;
    v7 = v11;
    if ( v10 )
      v7 = 1;
    v11 = v7;
    if ( v6 )
    {
      XMLObject = 0;
      if ( v11 )
      {
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        v11 = 0;
      }
      if ( v13 )
      {
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v13 = 0;
      }
    }
    else
    {
      v8 = operator new(0x18u);
      if ( v8 )
      {
        *v8 = &NodeFactory::`vftable';
        v8[1] = 1;
        v8[2] = 0;
      }
      else
      {
        v8 = 0;
      }
      v14 = v8;
      if ( !v8 )
      {
        if ( v11 )
        {
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v11 = 0;
        }
        if ( v13 )
        {
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v13 = 0;
        }
        if ( (v17 & 8) != 0 )
          operator delete(v5);
        XMLObject = -2147024882;
        goto LABEL_79;
      }
      v15 = 1;
      v8[2] = this;
      XMLObject = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v12 + 24LL))(v12, v8);
      if ( XMLObject >= 0 )
      {
        XMLObject = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 128LL))(v12, v10);
        if ( XMLObject >= 0 )
        {
          XMLObject = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 192LL))(v12, 0xFFFFFFFFLL);
          if ( XMLObject >= 0 )
          {
            (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
            v15 = 0;
            if ( v11 )
            {
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              v11 = 0;
            }
            if ( v13 )
            {
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              v13 = 0;
            }
          }
          else
          {
            (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
            v15 = 0;
            if ( v11 )
            {
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              v11 = 0;
            }
            if ( v13 )
            {
              if ( v12 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              v13 = 0;
            }
          }
        }
        else
        {
          (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
          v15 = 0;
          if ( v11 )
          {
            if ( v10 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            v11 = 0;
          }
          if ( v13 )
          {
            if ( v12 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            v13 = 0;
          }
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
        v15 = 0;
        if ( v11 )
        {
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v11 = 0;
        }
        if ( v13 )
        {
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v13 = 0;
        }
      }
    }
    if ( (v17 & 8) != 0 )
    {
      v4 = v5;
      goto LABEL_11;
    }
  }
  else
  {
    if ( v13 )
    {
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v13 = 0;
    }
    if ( (v17 & 8) != 0 )
    {
      v4 = lpMem;
LABEL_11:
      operator delete(v4);
    }
  }
LABEL_79:
  if ( (v20 & 8) != 0 )
    operator delete(v21);
  return (unsigned int)XMLObject;
}

```

## disassembly

```asm
0x180001808  mov     [rsp-8+arg_0], rbx
0x18000180d  mov     [rsp-8+arg_10], rsi
0x180001812  push    rbp
0x180001813  push    r12
0x180001815  push    r13
0x180001817  push    r14
0x180001819  push    r15
0x18000181b  lea     rbp, [rsp-37h]
0x180001820  sub     rsp, 90h
0x180001827  mov     r15, rcx
0x18000182a  xor     r12d, r12d
0x18000182d  mov     [rbp+57h+var_90], r12d
0x180001831  mov     esi, r12d
0x180001834  lea     r14d, [r12+2]
0x180001839  mov     [rbp+57h+var_40], r14d
0x18000183d  mov     [rbp+57h+var_3C], r14d
0x180001841  lea     ebx, [r12+10h]
0x180001846  mov     [rbp+57h+var_38], ebx
0x180001849  lea     r13, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180001850  mov     [rbp+57h+var_30], r13
0x180001854  lea     rdx, [rbp+57h+var_40]; struct SString *
0x180001858  call    ?GetHighestVersionedExclusionFile@AssemblyExclusion@@AEAA_NAEAVSString@@@Z; AssemblyExclusion::GetHighestVersionedExclusionFile(SString &)
0x18000185d  test    al, al
0x18000185f  jz      loc_180001C59
0x180001865  mov     [rbp+57h+var_58], r14d
0x180001869  mov     [rbp+57h+var_54], r14d
0x18000186d  mov     [rbp+57h+var_50], ebx
0x180001870  mov     [rbp+57h+lpMem], r13
0x180001874  lea     rcx, [rbp+57h+var_58]; this
0x180001878  call    ?GetVersionDirectoryPathFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryPathFromCurrentModulePath(SString &)
0x18000187d  lea     rdx, asc_180049544; "\\"
0x180001884  lea     rcx, [rbp+57h+var_58]; this
0x180001888  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18000188d  lea     rdx, [rbp+57h+var_40]; struct SString *
0x180001891  lea     rcx, [rbp+57h+var_58]; this
0x180001895  call    ?Append@SString@@QEAAXAEBV1@@Z; SString::Append(SString const &)
0x18000189a  mov     [rbp+57h+var_78], r12
0x18000189e  mov     [rbp+57h+var_70], r12d
0x1800018a2  mov     [rbp+57h+var_88], r12
0x1800018a6  mov     [rbp+57h+var_80], r12d
0x1800018aa  mov     [rbp+57h+var_68], r12
0x1800018ae  mov     [rbp+57h+var_60], r12d
0x1800018b2  lea     rax, [rbp+57h+var_78]
0x1800018b6  mov     [rbp+57h+arg_8], rax
0x1800018ba  mov     [rbp+57h+var_78], r12
0x1800018be  lea     r13d, [r12+1]
0x1800018c3  mov     [rbp+57h+var_90], r13d
0x1800018c7  lea     rcx, [rbp+57h+var_78]
0x1800018cb  call    cs:__imp_GetXMLObject
0x1800018d1  mov     esi, eax
0x1800018d3  mov     ebx, r13d
0x1800018d6  and     ebx, 0FFFFFFFEh
0x1800018d9  mov     [rbp+57h+var_90], ebx
0x1800018dc  mov     eax, [rbp+57h+var_70]
0x1800018df  cmp     [rbp+57h+var_78], r12
0x1800018e3  cmovnz  eax, r13d
0x1800018e7  mov     [rbp+57h+var_70], eax
0x1800018ea  test    esi, esi
0x1800018ec  jns     short loc_180001946
0x1800018ee  cmp     [rbp+57h+var_80], r12d
0x1800018f2  jz      short loc_18000190E
0x1800018f4  mov     rcx, [rbp+57h+var_88]
0x1800018f8  test    rcx, rcx
0x1800018fb  jz      short loc_18000190A
0x1800018fd  mov     rax, [rcx]
0x180001900  mov     rax, [rax+10h]
0x180001904  call    cs:__guard_dispatch_icall_fptr
0x18000190a  mov     [rbp+57h+var_80], r12d
0x18000190e  cmp     [rbp+57h+var_70], r12d
0x180001912  jz      short loc_18000192E
0x180001914  mov     rcx, [rbp+57h+var_78]
0x180001918  test    rcx, rcx
0x18000191b  jz      short loc_18000192A
0x18000191d  mov     rax, [rcx]
0x180001920  mov     rax, [rax+10h]
0x180001924  call    cs:__guard_dispatch_icall_fptr
0x18000192a  mov     [rbp+57h+var_70], r12d
0x18000192e  test    byte ptr [rbp+57h+var_50], 8
0x180001932  jz      loc_180001C59
0x180001938  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18000193c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001941  jmp     loc_180001C59
0x180001946  lea     rax, [rbp+57h+var_88]
0x18000194a  mov     [rbp+57h+arg_8], rax
0x18000194e  cmp     [rbp+57h+var_80], r12d
0x180001952  jz      short loc_18000196E
0x180001954  mov     rcx, [rbp+57h+var_88]
0x180001958  test    rcx, rcx
0x18000195b  jz      short loc_18000196A
0x18000195d  mov     rax, [rcx]
0x180001960  mov     rax, [rax+10h]
0x180001964  call    cs:__guard_dispatch_icall_fptr
0x18000196a  mov     [rbp+57h+var_80], r12d
0x18000196e  mov     [rbp+57h+var_88], r12
0x180001972  or      ebx, r14d
0x180001975  mov     [rbp+57h+var_90], ebx
0x180001978  lea     rcx, [rbp+57h+var_58]; this
0x18000197c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180001981  lea     rdx, [rbp+57h+var_88]
0x180001985  mov     r14, [rbp+57h+lpMem]
0x180001989  mov     rcx, r14
0x18000198c  call    cs:__imp_CreateConfigStream
0x180001992  cmp     eax, 80070002h
0x180001997  setz    cl
0x18000199a  and     ebx, 0FFFFFFFDh
0x18000199d  mov     [rbp+57h+var_90], ebx
0x1800019a0  mov     eax, [rbp+57h+var_80]
0x1800019a3  cmp     [rbp+57h+var_88], r12
0x1800019a7  cmovnz  eax, r13d
0x1800019ab  mov     [rbp+57h+var_80], eax
0x1800019ae  test    cl, cl
0x1800019b0  jz      short loc_180001A07
0x1800019b2  mov     esi, r12d
0x1800019b5  cmp     [rbp+57h+var_80], r12d
0x1800019b9  jz      short loc_1800019D5
0x1800019bb  mov     rcx, [rbp+57h+var_88]
0x1800019bf  test    rcx, rcx
0x1800019c2  jz      short loc_1800019D1
0x1800019c4  mov     rax, [rcx]
0x1800019c7  mov     rax, [rax+10h]
0x1800019cb  call    cs:__guard_dispatch_icall_fptr
0x1800019d1  mov     [rbp+57h+var_80], r12d
0x1800019d5  cmp     [rbp+57h+var_70], r12d
0x1800019d9  jz      short loc_1800019F5
0x1800019db  mov     rcx, [rbp+57h+var_78]
0x1800019df  test    rcx, rcx
0x1800019e2  jz      short loc_1800019F1
0x1800019e4  mov     rax, [rcx]
0x1800019e7  mov     rax, [rax+10h]
0x1800019eb  call    cs:__guard_dispatch_icall_fptr
0x1800019f1  mov     [rbp+57h+var_70], r12d
0x1800019f5  test    byte ptr [rbp+57h+var_50], 8
0x1800019f9  jz      loc_180001C59
0x1800019ff  mov     rcx, r14
0x180001a02  jmp     loc_18000193C
0x180001a07  mov     ecx, 18h; dwBytes
0x180001a0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001a11  mov     rbx, rax
0x180001a14  mov     [rbp+57h+arg_8], rax
0x180001a18  test    rax, rax
0x180001a1b  jz      short loc_180001A35
0x180001a1d  lea     rax, ??_7NodeFactory@@6B@; const NodeFactory::`vftable'
0x180001a24  mov     [rbx], rax
0x180001a27  mov     qword ptr [rbx+8], 1
0x180001a2f  mov     [rbx+10h], r12
0x180001a33  jmp     short loc_180001A38
0x180001a35  mov     rbx, r12
0x180001a38  mov     [rbp+57h+var_68], rbx
0x180001a3c  test    rbx, rbx
0x180001a3f  jz      loc_180001C06
0x180001a45  mov     [rbp+57h+var_60], r13d
0x180001a49  mov     [rbx+10h], r15
0x180001a4d  mov     rcx, [rbp+57h+var_78]
0x180001a51  mov     rax, [rcx]
0x180001a54  mov     rdx, rbx
0x180001a57  mov     rax, [rax+18h]
0x180001a5b  call    cs:__guard_dispatch_icall_fptr
0x180001a61  mov     esi, eax
0x180001a63  test    eax, eax
0x180001a65  jns     short loc_180001AC0
0x180001a67  mov     rax, [rbx]
0x180001a6a  mov     rcx, rbx
0x180001a6d  mov     rax, [rax+10h]
0x180001a71  call    cs:__guard_dispatch_icall_fptr
0x180001a77  mov     [rbp+57h+var_60], r12d
0x180001a7b  cmp     [rbp+57h+var_80], r12d
0x180001a7f  jz      short loc_180001A9B
0x180001a81  mov     rcx, [rbp+57h+var_88]
0x180001a85  test    rcx, rcx
0x180001a88  jz      short loc_180001A97
0x180001a8a  mov     rax, [rcx]
0x180001a8d  mov     rax, [rax+10h]
0x180001a91  call    cs:__guard_dispatch_icall_fptr
0x180001a97  mov     [rbp+57h+var_80], r12d
0x180001a9b  cmp     [rbp+57h+var_70], r12d
0x180001a9f  jz      short loc_180001ABB
0x180001aa1  mov     rcx, [rbp+57h+var_78]
0x180001aa5  test    rcx, rcx
0x180001aa8  jz      short loc_180001AB7
0x180001aaa  mov     rax, [rcx]
0x180001aad  mov     rax, [rax+10h]
0x180001ab1  call    cs:__guard_dispatch_icall_fptr
0x180001ab7  mov     [rbp+57h+var_70], r12d
0x180001abb  jmp     loc_1800019F5
0x180001ac0  mov     rcx, [rbp+57h+var_78]
0x180001ac4  mov     rax, [rcx]
0x180001ac7  mov     rdx, [rbp+57h+var_88]
0x180001acb  mov     rax, [rax+80h]
0x180001ad2  call    cs:__guard_dispatch_icall_fptr
0x180001ad8  mov     esi, eax
0x180001ada  test    eax, eax
0x180001adc  jns     short loc_180001B37
0x180001ade  mov     rax, [rbx]
0x180001ae1  mov     rcx, rbx
0x180001ae4  mov     rax, [rax+10h]
0x180001ae8  call    cs:__guard_dispatch_icall_fptr
0x180001aee  mov     [rbp+57h+var_60], r12d
0x180001af2  cmp     [rbp+57h+var_80], r12d
0x180001af6  jz      short loc_180001B12
0x180001af8  mov     rcx, [rbp+57h+var_88]
0x180001afc  test    rcx, rcx
0x180001aff  jz      short loc_180001B0E
0x180001b01  mov     rax, [rcx]
0x180001b04  mov     rax, [rax+10h]
0x180001b08  call    cs:__guard_dispatch_icall_fptr
0x180001b0e  mov     [rbp+57h+var_80], r12d
0x180001b12  cmp     [rbp+57h+var_70], r12d
0x180001b16  jz      short loc_180001B32
0x180001b18  mov     rcx, [rbp+57h+var_78]
0x180001b1c  test    rcx, rcx
0x180001b1f  jz      short loc_180001B2E
0x180001b21  mov     rax, [rcx]
0x180001b24  mov     rax, [rax+10h]
0x180001b28  call    cs:__guard_dispatch_icall_fptr
0x180001b2e  mov     [rbp+57h+var_70], r12d
0x180001b32  jmp     loc_1800019F5
0x180001b37  mov     rcx, [rbp+57h+var_78]
0x180001b3b  mov     rax, [rcx]
0x180001b3e  or      edx, 0FFFFFFFFh
0x180001b41  mov     rax, [rax+0C0h]
0x180001b48  call    cs:__guard_dispatch_icall_fptr
0x180001b4e  mov     esi, eax
0x180001b50  test    eax, eax
0x180001b52  jns     short loc_180001BAD
0x180001b54  mov     rax, [rbx]
0x180001b57  mov     rcx, rbx
0x180001b5a  mov     rax, [rax+10h]
0x180001b5e  call    cs:__guard_dispatch_icall_fptr
0x180001b64  mov     [rbp+57h+var_60], r12d
0x180001b68  cmp     [rbp+57h+var_80], r12d
0x180001b6c  jz      short loc_180001B88
0x180001b6e  mov     rcx, [rbp+57h+var_88]
0x180001b72  test    rcx, rcx
0x180001b75  jz      short loc_180001B84
0x180001b77  mov     rax, [rcx]
0x180001b7a  mov     rax, [rax+10h]
0x180001b7e  call    cs:__guard_dispatch_icall_fptr
0x180001b84  mov     [rbp+57h+var_80], r12d
0x180001b88  cmp     [rbp+57h+var_70], r12d
0x180001b8c  jz      short loc_180001BA8
0x180001b8e  mov     rcx, [rbp+57h+var_78]
0x180001b92  test    rcx, rcx
0x180001b95  jz      short loc_180001BA4
0x180001b97  mov     rax, [rcx]
0x180001b9a  mov     rax, [rax+10h]
0x180001b9e  call    cs:__guard_dispatch_icall_fptr
0x180001ba4  mov     [rbp+57h+var_70], r12d
0x180001ba8  jmp     loc_1800019F5
0x180001bad  mov     rax, [rbx]
0x180001bb0  mov     rcx, rbx
0x180001bb3  mov     rax, [rax+10h]
0x180001bb7  call    cs:__guard_dispatch_icall_fptr
0x180001bbd  mov     [rbp+57h+var_60], r12d
0x180001bc1  cmp     [rbp+57h+var_80], r12d
0x180001bc5  jz      short loc_180001BE1
0x180001bc7  mov     rcx, [rbp+57h+var_88]
0x180001bcb  test    rcx, rcx
0x180001bce  jz      short loc_180001BDD
0x180001bd0  mov     rax, [rcx]
0x180001bd3  mov     rax, [rax+10h]
0x180001bd7  call    cs:__guard_dispatch_icall_fptr
0x180001bdd  mov     [rbp+57h+var_80], r12d
0x180001be1  cmp     [rbp+57h+var_70], r12d
0x180001be5  jz      short loc_180001C01
0x180001be7  mov     rcx, [rbp+57h+var_78]
0x180001beb  test    rcx, rcx
0x180001bee  jz      short loc_180001BFD
0x180001bf0  mov     rax, [rcx]
0x180001bf3  mov     rax, [rax+10h]
0x180001bf7  call    cs:__guard_dispatch_icall_fptr
0x180001bfd  mov     [rbp+57h+var_70], r12d
0x180001c01  jmp     loc_1800019F5
0x180001c06  cmp     [rbp+57h+var_80], r12d
0x180001c0a  jz      short loc_180001C26
0x180001c0c  mov     rcx, [rbp+57h+var_88]
0x180001c10  test    rcx, rcx
0x180001c13  jz      short loc_180001C22
0x180001c15  mov     rax, [rcx]
0x180001c18  mov     rax, [rax+10h]
0x180001c1c  call    cs:__guard_dispatch_icall_fptr
0x180001c22  mov     [rbp+57h+var_80], r12d
0x180001c26  cmp     [rbp+57h+var_70], r12d
0x180001c2a  jz      short loc_180001C46
0x180001c2c  mov     rcx, [rbp+57h+var_78]
0x180001c30  test    rcx, rcx
0x180001c33  jz      short loc_180001C42
0x180001c35  mov     rax, [rcx]
0x180001c38  mov     rax, [rax+10h]
0x180001c3c  call    cs:__guard_dispatch_icall_fptr
0x180001c42  mov     [rbp+57h+var_70], r12d
0x180001c46  test    byte ptr [rbp+57h+var_50], 8
0x180001c4a  jz      short loc_180001C54
0x180001c4c  mov     rcx, r14; lpMem
0x180001c4f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001c54  mov     esi, 8007000Eh
0x180001c59  test    byte ptr [rbp+57h+var_38], 8
0x180001c5d  jz      short loc_180001C68
0x180001c5f  mov     rcx, [rbp+57h+var_30]; lpMem
0x180001c63  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001c68  mov     eax, esi
  ... truncated ...
```
