# CRasDiagHelper::GetLowerHypotheses(ulong *,tagHYPOTHESIS * *)

- ea: `0x180006ac0`
- end: `0x180006f8c`
- name: `?GetLowerHypotheses@CRasDiagHelper@@UEAAJPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `1228`
- prototype: `__int64 __fastcall(CRasDiagHelper *__hidden this, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006100`
- `0x180006274`
- `0x18000678c`
- `0x180006800`
- `0x180006ac0`
- `0x180007dc0`
- `0x180008084`
- `0x18000dab4`
- `0x18000dc5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006bca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006b74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006c70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e6c`

## pseudocode

```c
__int64 __fastcall CRasDiagHelper::GetLowerHypotheses(
        CRasDiagHelper *this,
        unsigned int *a2,
        struct tagHYPOTHESIS **a3)
{
  __int64 v4; // rdx
  const wchar_t *v5; // rdi
  const wchar_t *v6; // rax
  __int64 v7; // rbx
  WCHAR *v8; // rax
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  wchar_t v11; // r8
  WCHAR *v12; // rcx
  struct tagHELPER_ATTRIBUTE *v13; // r12
  __int64 v14; // rdx
  const wchar_t *v15; // rdi
  const wchar_t *v16; // rax
  __int64 v17; // rbx
  WCHAR *v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rcx
  wchar_t v21; // r8
  WCHAR *v22; // rcx
  unsigned int v23; // r15d
  int v24; // r14d
  WCHAR *v25; // r8
  __int64 v26; // rdx
  const wchar_t *v27; // rdi
  const wchar_t *v28; // rax
  __int64 v29; // rbx
  WCHAR *v30; // rax
  unsigned __int64 v31; // rdx
  __int64 v32; // rcx
  wchar_t v33; // r9
  WCHAR *v34; // rcx
  int v35; // r14d
  WCHAR *v36; // r8
  __int64 v37; // rcx
  const wchar_t *v38; // rdi
  const wchar_t *v39; // rax
  __int64 v40; // rbx
  WCHAR *v41; // rax
  unsigned __int64 v42; // rdx
  __int64 v43; // r9
  wchar_t v44; // cx
  WCHAR *v45; // rcx
  unsigned int *v46; // r9
  LPVOID pv_8[2]; // [rsp+28h] [rbp-99h] BYREF
  _QWORD v49[3]; // [rsp+38h] [rbp-89h]
  tagHELPER_ATTRIBUTE v50; // [rsp+50h] [rbp-71h] BYREF

  if ( a2 )
  {
    if ( a3 )
    {
      *a2 = 0;
      *a3 = 0;
      if ( !*((_DWORD *)this + 293) )
      {
        *(_OWORD *)pv_8 = 0;
        LODWORD(v49[0]) = 0;
        *(_OWORD *)&v49[1] = 0;
        _hypothesis_builder::FreeAll(pv_8);
        CoTaskMemFree(pv_8[0]);
        pv_8[0] = 0;
        if ( (int)StringCchCopyWithAlloc((unsigned __int16 **)pv_8, 0xFFFFu, L"CVPNDiagHelper") >= 0 )
          _hypothesis_builder::SetCount((_hypothesis_builder *)pv_8, 4u);
        CoTaskMemFree(0);
        v50.pwszName = 0;
        v4 = 65534;
        v5 = L"entryname";
        v6 = L"entryname";
        do
        {
          if ( !*v6 )
            break;
          ++v6;
          --v4;
        }
        while ( v4 );
        v7 = (65534 - v4) & -(__int64)(v4 != 0);
        if ( v4 )
        {
          v8 = (WCHAR *)CoTaskMemAlloc(2 * v7 + 2);
          v50.pwszName = v8;
          if ( v8 )
          {
            v9 = v7 + 1;
            if ( v7 != -1 )
            {
              if ( v9 <= 0x7FFFFFFF )
              {
                v10 = 2147483646;
                do
                {
                  if ( !v10 )
                    break;
                  v11 = *v5;
                  if ( !*v5 )
                    break;
                  ++v5;
                  *v8++ = v11;
                  --v10;
                  --v9;
                }
                while ( v9 );
                v12 = v8 - 1;
                if ( v9 )
                  v12 = v8;
                *v12 = 0;
              }
              else
              {
                *v8 = 0;
              }
            }
          }
        }
        v50.type = AT_STRING;
        v50.Int64 = 0;
        _attribute_t::SetValue((_attribute_t *)&v50, (const unsigned __int16 *)this + 68);
        v13 = (struct tagHELPER_ATTRIBUTE *)v49[1];
        if ( v50.type && v50.pwszName )
          _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)v49[1], &v50);
        _attribute_t::FreeAll((LPVOID *)&v50.pwszName);
        CoTaskMemFree(0);
        v50.pwszName = 0;
        v14 = 65534;
        v15 = L"phonebook";
        v16 = L"phonebook";
        do
        {
          if ( !*v16 )
            break;
          ++v16;
          --v14;
        }
        while ( v14 );
        v17 = (65534 - v14) & -(__int64)(v14 != 0);
        if ( v14 )
        {
          v18 = (WCHAR *)CoTaskMemAlloc(2 * v17 + 2);
          v50.pwszName = v18;
          if ( v18 )
          {
            v19 = v17 + 1;
            if ( v17 != -1 )
            {
              if ( v19 <= 0x7FFFFFFF )
              {
                v20 = 2147483646;
                do
                {
                  if ( !v20 )
                    break;
                  v21 = *v15;
                  if ( !*v15 )
                    break;
                  ++v15;
                  *v18++ = v21;
                  --v20;
                  --v19;
                }
                while ( v19 );
                v22 = v18 - 1;
                if ( v19 )
                  v22 = v18;
                *v22 = 0;
              }
              else
              {
                *v18 = 0;
              }
            }
          }
        }
        v50.type = AT_STRING;
        v50.Int64 = 0;
        _attribute_t::SetValue((_attribute_t *)&v50, (const unsigned __int16 *)this + 325);
        v23 = v49[0];
        if ( LODWORD(v49[0]) && v50.type && v50.pwszName )
          _attribute_t::Copy(v13 + 1, &v50);
        _attribute_t::FreeAll((LPVOID *)&v50.pwszName);
        v24 = *((_DWORD *)this + 32);
        CoTaskMemFree(0);
        v25 = 0;
        v50.pwszName = 0;
        v26 = 65534;
        v27 = L"ErrorCode";
        v28 = L"ErrorCode";
        do
        {
          if ( !*v28 )
            break;
          ++v28;
          --v26;
        }
        while ( v26 );
        v29 = (65534 - v26) & -(__int64)(v26 != 0);
        if ( v26 )
        {
          v30 = (WCHAR *)CoTaskMemAlloc(2 * v29 + 2);
          v25 = v30;
          v50.pwszName = v30;
          if ( v30 )
          {
            v31 = v29 + 1;
            if ( v29 != -1 )
            {
              if ( v31 <= 0x7FFFFFFF )
              {
                v32 = 2147483646;
                do
                {
                  if ( !v32 )
                    break;
                  v33 = *v27;
                  if ( !*v27 )
                    break;
                  ++v27;
                  *v30++ = v33;
                  --v32;
                  --v31;
                }
                while ( v31 );
                v34 = v30 - 1;
                if ( v31 )
                  v34 = v30;
                *v34 = 0;
              }
              else
              {
                *v30 = 0;
              }
            }
          }
        }
        v50.type = AT_UINT32;
        v50.Boolean = v24;
        if ( v23 >= 2 && v25 )
          _attribute_t::Copy(v13 + 2, &v50);
        _attribute_t::FreeAll((LPVOID *)&v50.pwszName);
        v35 = *((unsigned __int8 *)this + 1176);
        CoTaskMemFree(0);
        v36 = 0;
        v50.pwszName = 0;
        v37 = 65534;
        v38 = L"IsCMConnection";
        v39 = L"IsCMConnection";
        do
        {
          if ( !*v39 )
            break;
          ++v39;
          --v37;
        }
        while ( v37 );
        v40 = (65534 - v37) & -(__int64)(v37 != 0);
        if ( v37 )
        {
          v41 = (WCHAR *)CoTaskMemAlloc(2 * v40 + 2);
          v36 = v41;
          v50.pwszName = v41;
          if ( v41 )
          {
            v42 = v40 + 1;
            if ( v40 != -1 )
            {
              if ( v42 <= 0x7FFFFFFF )
              {
                v43 = 2147483646;
                do
                {
                  if ( !v43 )
                    break;
                  v44 = *v38;
                  if ( !*v38 )
                    break;
                  ++v38;
                  *v41++ = v44;
                  --v43;
                  --v42;
                }
                while ( v42 );
                v45 = v41 - 1;
                if ( v42 )
                  v45 = v41;
                *v45 = 0;
              }
              else
              {
                *v41 = 0;
              }
            }
          }
        }
        v50.type = AT_BOOLEAN;
        v50.Boolean = v35;
        if ( v23 >= 3 && v36 )
          _attribute_t::Copy(v13 + 3, &v50);
        _attribute_t::FreeAll((LPVOID *)&v50.pwszName);
        _hypothesis_builder::Detach((_hypothesis_builder *)pv_8, a2, a3, v46);
        _hypothesis_builder::~_hypothesis_builder(pv_8);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006ac0  mov     rax, rsp
0x180006ac3  mov     [rax+8], rbx
0x180006ac7  mov     [rax+18h], r8
0x180006acb  mov     [rax+10h], rdx
0x180006acf  push    rbp
0x180006ad0  push    rsi
0x180006ad1  push    rdi
0x180006ad2  push    r12
0x180006ad4  push    r13
0x180006ad6  push    r14
0x180006ad8  push    r15
0x180006ada  lea     rbp, [rax-5Fh]
0x180006ade  sub     rsp, 0E0h
0x180006ae5  mov     rax, r8
0x180006ae8  mov     r13, rcx
0x180006aeb  xor     r15d, r15d
0x180006aee  test    rdx, rdx
0x180006af1  jz      loc_180006F6E
0x180006af7  test    rax, rax
0x180006afa  jz      loc_180006F6E
0x180006b00  mov     [rdx], r15d
0x180006b03  mov     [r8], r15
0x180006b06  cmp     [rcx+494h], r15d
0x180006b0d  jnz     loc_180006F6E
0x180006b13  xorps   xmm0, xmm0
0x180006b16  movdqu  xmmword ptr [rsp+110h+pv+8], xmm0
0x180006b1c  mov     dword ptr [rsp+110h+var_E0], r15d
0x180006b21  xorps   xmm1, xmm1
0x180006b24  movdqu  xmmword ptr [rsp+110h+var_E0+8], xmm1
0x180006b2a  lea     rcx, [rsp+110h+pv+8]; this
0x180006b2f  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x180006b34  mov     rcx, [rsp+110h+pv+8]; pv
0x180006b39  call    cs:__imp_CoTaskMemFree
0x180006b40  nop     dword ptr [rax+rax+00h]
0x180006b45  mov     [rsp+110h+pv+8], r15
0x180006b4a  lea     r8, aCvpndiaghelper; "CVPNDiagHelper"
0x180006b51  mov     edx, 0FFFFh; unsigned __int64
0x180006b56  lea     rcx, [rsp+110h+pv+8]; unsigned __int16 **
0x180006b5b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180006b60  test    eax, eax
0x180006b62  js      short loc_180006B72
0x180006b64  lea     edx, [r15+4]; unsigned int
0x180006b68  lea     rcx, [rsp+110h+pv+8]; this
0x180006b6d  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x180006b72  xor     ecx, ecx; pv
0x180006b74  call    cs:__imp_CoTaskMemFree
0x180006b7b  nop     dword ptr [rax+rax+00h]
0x180006b80  mov     [rbp+57h+var_C8.pwszName], r15
0x180006b84  mov     esi, 0FFFEh
0x180006b89  mov     edx, esi
0x180006b8b  lea     rdi, aEntryname; "entryname"
0x180006b92  mov     rax, rdi
0x180006b95  cmp     [rax], r15w
0x180006b99  jz      short loc_180006BA5
0x180006b9b  add     rax, 2
0x180006b9f  sub     rdx, 1
0x180006ba3  jnz     short loc_180006B95
0x180006ba5  mov     rax, rdx
0x180006ba8  mov     rcx, rsi
0x180006bab  sub     rcx, rdx
0x180006bae  neg     rax
0x180006bb1  sbb     rbx, rbx
0x180006bb4  and     rbx, rcx
0x180006bb7  mov     r14d, 7FFFFFFEh
0x180006bbd  test    rdx, rdx
0x180006bc0  jz      short loc_180006C2D
0x180006bc2  lea     rcx, ds:2[rbx*2]; cb
0x180006bca  call    cs:__imp_CoTaskMemAlloc
0x180006bd1  nop     dword ptr [rax+rax+00h]
0x180006bd6  mov     [rbp+57h+var_C8.pwszName], rax
0x180006bda  test    rax, rax
0x180006bdd  jz      short loc_180006C2D
0x180006bdf  lea     rdx, [rbx+1]
0x180006be3  test    rdx, rdx
0x180006be6  jz      short loc_180006C2D
0x180006be8  cmp     rdx, 7FFFFFFFh
0x180006bef  jbe     short loc_180006BF7
0x180006bf1  mov     [rax], r15w
0x180006bf5  jmp     short loc_180006C2D
0x180006bf7  mov     rcx, r14
0x180006bfa  test    rcx, rcx
0x180006bfd  jz      short loc_180006C1E
0x180006bff  movzx   r8d, word ptr [rdi]
0x180006c03  test    r8w, r8w
0x180006c07  jz      short loc_180006C1E
0x180006c09  add     rdi, 2
0x180006c0d  mov     [rax], r8w
0x180006c11  add     rax, 2
0x180006c15  dec     rcx
0x180006c18  sub     rdx, 1
0x180006c1c  jnz     short loc_180006BFA
0x180006c1e  lea     rcx, [rax-2]
0x180006c22  test    rdx, rdx
0x180006c25  cmovnz  rcx, rax
0x180006c29  mov     [rcx], r15w
0x180006c2d  mov     [rbp+57h+var_C8.type], 0Ah
0x180006c34  mov     qword ptr [rbp+57h+var_C8.10h], r15
0x180006c38  lea     rdx, [r13+88h]; unsigned __int16 *
0x180006c3f  lea     rcx, [rbp+57h+var_C8]; this
0x180006c43  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x180006c48  mov     r12, qword ptr [rsp+110h+var_E0+8]
0x180006c4d  cmp     [rbp+57h+var_C8.type], r15d
0x180006c51  jz      short loc_180006C65
0x180006c53  cmp     [rbp+57h+var_C8.pwszName], r15
0x180006c57  jz      short loc_180006C65
0x180006c59  lea     rdx, [rbp+57h+var_C8]; struct tagHELPER_ATTRIBUTE *
0x180006c5d  mov     rcx, r12; this
0x180006c60  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180006c65  lea     rcx, [rbp+57h+var_C8]; this
0x180006c69  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180006c6e  xor     ecx, ecx; pv
0x180006c70  call    cs:__imp_CoTaskMemFree
0x180006c77  nop     dword ptr [rax+rax+00h]
0x180006c7c  mov     [rbp+57h+var_C8.pwszName], r15
0x180006c80  mov     rdx, rsi
0x180006c83  lea     rdi, aPhonebook; "phonebook"
0x180006c8a  mov     rax, rdi
0x180006c8d  cmp     [rax], r15w
0x180006c91  jz      short loc_180006C9D
0x180006c93  add     rax, 2
0x180006c97  sub     rdx, 1
0x180006c9b  jnz     short loc_180006C8D
0x180006c9d  mov     rax, rdx
0x180006ca0  mov     rcx, rsi
0x180006ca3  sub     rcx, rdx
0x180006ca6  neg     rax
0x180006ca9  sbb     rbx, rbx
0x180006cac  and     rbx, rcx
0x180006caf  test    rdx, rdx
0x180006cb2  jz      short loc_180006D1F
0x180006cb4  lea     rcx, ds:2[rbx*2]; cb
0x180006cbc  call    cs:__imp_CoTaskMemAlloc
0x180006cc3  nop     dword ptr [rax+rax+00h]
0x180006cc8  mov     [rbp+57h+var_C8.pwszName], rax
0x180006ccc  test    rax, rax
0x180006ccf  jz      short loc_180006D1F
0x180006cd1  lea     rdx, [rbx+1]
0x180006cd5  test    rdx, rdx
0x180006cd8  jz      short loc_180006D1F
0x180006cda  cmp     rdx, 7FFFFFFFh
0x180006ce1  jbe     short loc_180006CE9
0x180006ce3  mov     [rax], r15w
0x180006ce7  jmp     short loc_180006D1F
0x180006ce9  mov     rcx, r14
0x180006cec  test    rcx, rcx
0x180006cef  jz      short loc_180006D10
0x180006cf1  movzx   r8d, word ptr [rdi]
0x180006cf5  test    r8w, r8w
0x180006cf9  jz      short loc_180006D10
0x180006cfb  add     rdi, 2
0x180006cff  mov     [rax], r8w
0x180006d03  add     rax, 2
0x180006d07  dec     rcx
0x180006d0a  sub     rdx, 1
0x180006d0e  jnz     short loc_180006CEC
0x180006d10  lea     rcx, [rax-2]
0x180006d14  test    rdx, rdx
0x180006d17  cmovnz  rcx, rax
0x180006d1b  mov     [rcx], r15w
0x180006d1f  mov     [rbp+57h+var_C8.type], 0Ah
0x180006d26  mov     qword ptr [rbp+57h+var_C8.10h], r15
0x180006d2a  lea     rdx, [r13+28Ah]; unsigned __int16 *
0x180006d31  lea     rcx, [rbp+57h+var_C8]; this
0x180006d35  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x180006d3a  mov     r15d, dword ptr [rsp+110h+var_E0]
0x180006d3f  cmp     r15d, 1
0x180006d43  jb      short loc_180006D63
0x180006d45  cmp     [rbp+57h+var_C8.type], 0
0x180006d49  jz      short loc_180006D63
0x180006d4b  cmp     [rbp+57h+var_C8.pwszName], 0
0x180006d50  jz      short loc_180006D63
0x180006d52  lea     rcx, [r12+90h]; this
0x180006d5a  lea     rdx, [rbp+57h+var_C8]; struct tagHELPER_ATTRIBUTE *
0x180006d5e  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180006d63  lea     rcx, [rbp+57h+var_C8]; this
0x180006d67  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180006d6c  mov     r14d, [r13+80h]
0x180006d73  xor     ecx, ecx; pv
0x180006d75  call    cs:__imp_CoTaskMemFree
0x180006d7c  nop     dword ptr [rax+rax+00h]
0x180006d81  xor     r10d, r10d
0x180006d84  mov     r8d, r10d
0x180006d87  mov     [rbp+57h+var_C8.pwszName], r10
0x180006d8b  mov     rdx, rsi
0x180006d8e  lea     rdi, aErrorcode; "ErrorCode"
0x180006d95  mov     rax, rdi
0x180006d98  cmp     [rax], r10w
0x180006d9c  jz      short loc_180006DA8
0x180006d9e  add     rax, 2
0x180006da2  sub     rdx, 1
0x180006da6  jnz     short loc_180006D98
0x180006da8  mov     rax, rdx
0x180006dab  mov     rcx, rsi
0x180006dae  sub     rcx, rdx
0x180006db1  neg     rax
0x180006db4  sbb     rbx, rbx
0x180006db7  and     rbx, rcx
0x180006dba  test    rdx, rdx
0x180006dbd  jz      short loc_180006E32
0x180006dbf  lea     rcx, ds:2[rbx*2]; cb
0x180006dc7  call    cs:__imp_CoTaskMemAlloc
0x180006dce  nop     dword ptr [rax+rax+00h]
0x180006dd3  mov     r8, rax
0x180006dd6  mov     [rbp+57h+var_C8.pwszName], rax
0x180006dda  xor     r10d, r10d
0x180006ddd  test    rax, rax
0x180006de0  jz      short loc_180006E32
0x180006de2  lea     rdx, [rbx+1]
0x180006de6  test    rdx, rdx
0x180006de9  jz      short loc_180006E32
0x180006deb  cmp     rdx, 7FFFFFFFh
0x180006df2  jbe     short loc_180006DFA
0x180006df4  mov     [rax], r10w
0x180006df8  jmp     short loc_180006E32
0x180006dfa  mov     ecx, 7FFFFFFEh
0x180006dff  test    rcx, rcx
0x180006e02  jz      short loc_180006E23
0x180006e04  movzx   r9d, word ptr [rdi]
0x180006e08  test    r9w, r9w
0x180006e0c  jz      short loc_180006E23
0x180006e0e  add     rdi, 2
0x180006e12  mov     [rax], r9w
0x180006e16  add     rax, 2
0x180006e1a  dec     rcx
0x180006e1d  sub     rdx, 1
0x180006e21  jnz     short loc_180006DFF
0x180006e23  lea     rcx, [rax-2]
0x180006e27  test    rdx, rdx
0x180006e2a  cmovnz  rcx, rax
0x180006e2e  mov     [rcx], r10w
0x180006e32  mov     [rbp+57h+var_C8.type], 7
0x180006e39  mov     dword ptr [rbp+57h+var_C8.10h], r14d
0x180006e3d  cmp     r15d, 2
0x180006e41  jb      short loc_180006E59
0x180006e43  test    r8, r8
0x180006e46  jz      short loc_180006E59
0x180006e48  lea     rcx, [r12+120h]; this
0x180006e50  lea     rdx, [rbp+57h+var_C8]; struct tagHELPER_ATTRIBUTE *
0x180006e54  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180006e59  lea     rcx, [rbp+57h+var_C8]; this
0x180006e5d  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180006e62  movzx   r14d, byte ptr [r13+498h]
0x180006e6a  xor     ecx, ecx; pv
0x180006e6c  call    cs:__imp_CoTaskMemFree
0x180006e73  nop     dword ptr [rax+rax+00h]
0x180006e78  xor     r13d, r13d
0x180006e7b  mov     r8d, r13d
0x180006e7e  mov     [rbp+57h+var_C8.pwszName], r13
0x180006e82  mov     rcx, rsi
0x180006e85  lea     rdi, aIscmconnection; "IsCMConnection"
0x180006e8c  mov     rax, rdi
0x180006e8f  cmp     [rax], r13w
0x180006e93  jz      short loc_180006E9F
0x180006e95  add     rax, 2
0x180006e99  sub     rcx, 1
0x180006e9d  jnz     short loc_180006E8F
0x180006e9f  mov     rax, rcx
0x180006ea2  sub     rsi, rcx
0x180006ea5  neg     rax
0x180006ea8  sbb     rbx, rbx
0x180006eab  and     rbx, rsi
0x180006eae  test    rcx, rcx
0x180006eb1  jz      short loc_180006F21
0x180006eb3  lea     rcx, ds:2[rbx*2]; cb
0x180006ebb  call    cs:__imp_CoTaskMemAlloc
0x180006ec2  nop     dword ptr [rax+rax+00h]
0x180006ec7  mov     r8, rax
0x180006eca  mov     [rbp+57h+var_C8.pwszName], rax
0x180006ece  test    rax, rax
0x180006ed1  jz      short loc_180006F21
0x180006ed3  lea     rdx, [rbx+1]
0x180006ed7  test    rdx, rdx
0x180006eda  jz      short loc_180006F21
0x180006edc  cmp     rdx, 7FFFFFFFh
0x180006ee3  jbe     short loc_180006EEB
0x180006ee5  mov     [rax], r13w
0x180006ee9  jmp     short loc_180006F21
0x180006eeb  mov     r9d, 7FFFFFFEh
0x180006ef1  test    r9, r9
0x180006ef4  jz      short loc_180006F12
0x180006ef6  movzx   ecx, word ptr [rdi]
0x180006ef9  test    cx, cx
0x180006efc  jz      short loc_180006F12
0x180006efe  add     rdi, 2
0x180006f02  mov     [rax], cx
0x180006f05  add     rax, 2
0x180006f09  dec     r9
0x180006f0c  sub     rdx, 1
0x180006f10  jnz     short loc_180006EF1
0x180006f12  lea     rcx, [rax-2]
0x180006f16  test    rdx, rdx
0x180006f19  cmovnz  rcx, rax
0x180006f1d  mov     [rcx], r13w
0x180006f21  mov     [rbp+57h+var_C8.type], 1
0x180006f28  mov     dword ptr [rbp+57h+var_C8.10h], r14d
0x180006f2c  cmp     r15d, 3
0x180006f30  jb      short loc_180006F48
0x180006f32  test    r8, r8
0x180006f35  jz      short loc_180006F48
0x180006f37  lea     rcx, [r12+1B0h]; this
  ... truncated ...
```
