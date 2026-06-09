# DetectFactory::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x1800e5840`
- end: `0x1800e5a58`
- name: `?CreateNode@DetectFactory@@UEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(DetectFactory *__hidden this, struct IXMLNodeSource *, void *, unsigned __int16, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180037454`
- `0x180064820`
- `0x1800e5840`
- `0x180102cc6`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e58dd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e593b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e5a2c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e58dd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e593b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800e5a2c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5925`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5a1b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5925`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e5a1b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e58cd`
- `OLEAUT32!__imp_SysStringLen` at `0x1800e58cd`

## string_xrefs

- `0x1800e59ba`: `text/xslt+xml`

## pseudocode

```c
__int64 __fastcall DetectFactory::CreateNode(
        DetectFactory *this,
        struct IXMLNodeSource *a2,
        void *a3,
        __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  __int16 i; // bp
  __int64 v8; // rsi
  const unsigned __int16 *v9; // rbx
  OLECHAR *v10; // rcx
  UINT v11; // eax
  __int64 v12; // r12
  BSTR v13; // rax
  BSTR v14; // r15
  const unsigned __int16 *v15; // r10
  const unsigned __int16 *v16; // r10
  const unsigned __int16 *v17; // r10
  OLECHAR *v18; // rcx

  for ( i = a4; i; --i )
  {
    v8 = (__int64)*a5++;
    if ( *(_DWORD *)(v8 + 4) == 2 )
    {
      v18 = (OLECHAR *)*((_QWORD *)this + 4);
      if ( v18 )
        SysFreeString(v18);
      *((_QWORD *)this + 4) = 0;
      *((_QWORD *)this + 4) = SysAllocStringLen(*(const OLECHAR **)(v8 + 16), *(_DWORD *)(v8 + 24));
      *((_DWORD *)this + 12) = *(_DWORD *)(v8 + 24);
    }
    else if ( *(_DWORD *)(v8 + 4) == 13 )
    {
      v9 = (const unsigned __int16 *)*((_QWORD *)this + 4);
      if ( v9 )
      {
        if ( *((_DWORD *)this + 12) == 4 )
        {
          if ( (unsigned int)fastcmpni(*((const unsigned __int16 **)this + 4), L"href", 4u) )
          {
            if ( !(unsigned int)fastcmpni(v9, L"type", 4u) && *(_DWORD *)(v8 + 24) == 8 )
            {
              if ( (unsigned int)fastcmpi(*(const unsigned __int16 **)(v8 + 16), L"text/css") )
              {
                if ( !(unsigned int)fastcmpi(v15, L"text/xsl")
                  || !(unsigned int)fastcmpi(v16, L"text/xslt")
                  || !(unsigned int)fastcmpi(v17, L"text/xslt+xml") )
                {
                  *((_DWORD *)this + 13) = 2;
                }
              }
              else
              {
                *((_DWORD *)this + 13) = 1;
              }
            }
          }
          else
          {
            v10 = (OLECHAR *)*((_QWORD *)this + 5);
            if ( v10 )
            {
              v11 = SysStringLen(v10);
              v12 = v11;
              v13 = SysAllocStringLen(0, v11 + *(_DWORD *)(v8 + 24));
              v14 = v13;
              if ( v13 )
              {
                memcpy_0(v13, *((const void **)this + 5), 2 * v12);
                memcpy_0(&v14[v12], *(const void **)(v8 + 16), 2LL * *(unsigned int *)(v8 + 24));
                v14[(unsigned int)(v12 + *(_DWORD *)(v8 + 24))] = 0;
                SysFreeString(*((BSTR *)this + 5));
                *((_QWORD *)this + 5) = v14;
              }
            }
            else
            {
              *((_QWORD *)this + 5) = SysAllocStringLen(*(const OLECHAR **)(v8 + 16), *(_DWORD *)(v8 + 24));
            }
          }
        }
        else if ( *((_DWORD *)this + 12) == 9
               && !(unsigned int)fastcmpi(*((const unsigned __int16 **)this + 4), L"alternate")
               && *(_DWORD *)(v8 + 24) == 3
               && !(unsigned int)fastcmpi(*(const unsigned __int16 **)(v8 + 16), L"yes") )
        {
          *((_DWORD *)this + 14) = 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800e5840  push    rbx
0x1800e5842  push    rbp
0x1800e5843  push    rsi
0x1800e5844  push    rdi
0x1800e5845  push    r12
0x1800e5847  push    r13
0x1800e5849  push    r14
0x1800e584b  push    r15
0x1800e584d  sub     rsp, 28h
0x1800e5851  xor     r13d, r13d
0x1800e5854  movzx   ebp, r9w
0x1800e5858  mov     rdi, rcx
0x1800e585b  test    r9w, r9w
0x1800e585f  jz      loc_1800E5A45
0x1800e5865  mov     r14, [rsp+68h+arg_20]
0x1800e586d  mov     rsi, [r14]
0x1800e5870  mov     eax, 0FFFFh
0x1800e5875  add     bp, ax
0x1800e5878  lea     r14, [r14+8]
0x1800e587c  cmp     dword ptr [rsi+4], 2
0x1800e5880  jz      loc_1800E5A12
0x1800e5886  cmp     dword ptr [rsi+4], 0Dh
0x1800e588a  jnz     loc_1800E5A3C
0x1800e5890  mov     rbx, [rdi+20h]
0x1800e5894  test    rbx, rbx
0x1800e5897  jz      loc_1800E5A3C
0x1800e589d  cmp     dword ptr [rdi+30h], 4
0x1800e58a1  jnz     loc_1800E59D6
0x1800e58a7  mov     r8d, 4; unsigned __int64
0x1800e58ad  lea     rdx, aHref; "href"
0x1800e58b4  mov     rcx, rbx; unsigned __int16 *
0x1800e58b7  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x1800e58bc  test    eax, eax
0x1800e58be  jnz     loc_1800E594A
0x1800e58c4  mov     rcx, [rdi+28h]; pbstr
0x1800e58c8  test    rcx, rcx
0x1800e58cb  jz      short loc_1800E5934
0x1800e58cd  call    cs:__imp_SysStringLen
0x1800e58d3  mov     edx, [rsi+18h]
0x1800e58d6  xor     ecx, ecx; strIn
0x1800e58d8  add     edx, eax; ui
0x1800e58da  mov     r12d, eax
0x1800e58dd  call    cs:__imp_SysAllocStringLen
0x1800e58e3  mov     r15, rax
0x1800e58e6  test    rax, rax
0x1800e58e9  jz      loc_1800E5A3C
0x1800e58ef  mov     rdx, [rdi+28h]; Src
0x1800e58f3  lea     rbx, [r12+r12]
0x1800e58f7  mov     r8, rbx; Size
0x1800e58fa  mov     rcx, rax; void *
0x1800e58fd  call    memcpy_0
0x1800e5902  mov     r8d, [rsi+18h]
0x1800e5906  lea     rcx, [rbx+r15]; void *
0x1800e590a  mov     rdx, [rsi+10h]; Src
0x1800e590e  add     r8, r8; Size
0x1800e5911  call    memcpy_0
0x1800e5916  mov     eax, [rsi+18h]
0x1800e5919  add     eax, r12d
0x1800e591c  mov     [r15+rax*2], r13w
0x1800e5921  mov     rcx, [rdi+28h]; bstrString
0x1800e5925  call    cs:__imp_SysFreeString
0x1800e592b  mov     [rdi+28h], r15
0x1800e592f  jmp     loc_1800E5A3C
0x1800e5934  mov     edx, [rsi+18h]; ui
0x1800e5937  mov     rcx, [rsi+10h]; strIn
0x1800e593b  call    cs:__imp_SysAllocStringLen
0x1800e5941  mov     [rdi+28h], rax
0x1800e5945  jmp     loc_1800E5A3C
0x1800e594a  mov     r8d, 4; unsigned __int64
0x1800e5950  lea     rdx, aType; "type"
0x1800e5957  mov     rcx, rbx; unsigned __int16 *
0x1800e595a  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x1800e595f  test    eax, eax
0x1800e5961  jnz     loc_1800E5A3C
0x1800e5967  cmp     dword ptr [rsi+18h], 8
0x1800e596b  jnz     loc_1800E5A3C
0x1800e5971  mov     r10, [rsi+10h]
0x1800e5975  lea     rdx, aTextCss; "text/css"
0x1800e597c  mov     rcx, r10; unsigned __int16 *
0x1800e597f  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1800e5984  test    eax, eax
0x1800e5986  jnz     short loc_1800E5994
0x1800e5988  mov     dword ptr [rdi+34h], 1
0x1800e598f  jmp     loc_1800E5A3C
0x1800e5994  lea     rdx, aTextXsl; "text/xsl"
0x1800e599b  mov     rcx, r10; unsigned __int16 *
0x1800e599e  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1800e59a3  test    eax, eax
0x1800e59a5  jz      short loc_1800E59CD
0x1800e59a7  lea     rdx, aTextXslt; "text/xslt"
0x1800e59ae  mov     rcx, r10; unsigned __int16 *
0x1800e59b1  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1800e59b6  test    eax, eax
0x1800e59b8  jz      short loc_1800E59CD
0x1800e59ba  lea     rdx, aTextXsltXml; "text/xslt+xml"
0x1800e59c1  mov     rcx, r10; unsigned __int16 *
0x1800e59c4  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1800e59c9  test    eax, eax
0x1800e59cb  jnz     short loc_1800E5A3C
0x1800e59cd  mov     dword ptr [rdi+34h], 2
0x1800e59d4  jmp     short loc_1800E5A3C
0x1800e59d6  cmp     dword ptr [rdi+30h], 9
0x1800e59da  jnz     short loc_1800E5A3C
0x1800e59dc  lea     rdx, aAlternate; "alternate"
0x1800e59e3  mov     rcx, rbx; unsigned __int16 *
0x1800e59e6  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1800e59eb  test    eax, eax
0x1800e59ed  jnz     short loc_1800E5A3C
0x1800e59ef  cmp     dword ptr [rsi+18h], 3
0x1800e59f3  jnz     short loc_1800E5A3C
0x1800e59f5  mov     rcx, [rsi+10h]; unsigned __int16 *
0x1800e59f9  lea     rdx, aYes; "yes"
0x1800e5a00  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x1800e5a05  test    eax, eax
0x1800e5a07  jnz     short loc_1800E5A3C
0x1800e5a09  mov     dword ptr [rdi+38h], 1
0x1800e5a10  jmp     short loc_1800E5A3C
0x1800e5a12  mov     rcx, [rdi+20h]; bstrString
0x1800e5a16  test    rcx, rcx
0x1800e5a19  jz      short loc_1800E5A21
0x1800e5a1b  call    cs:__imp_SysFreeString
0x1800e5a21  mov     [rdi+20h], r13
0x1800e5a25  mov     edx, [rsi+18h]; ui
0x1800e5a28  mov     rcx, [rsi+10h]; strIn
0x1800e5a2c  call    cs:__imp_SysAllocStringLen
0x1800e5a32  mov     [rdi+20h], rax
0x1800e5a36  mov     eax, [rsi+18h]
0x1800e5a39  mov     [rdi+30h], eax
0x1800e5a3c  test    bp, bp
0x1800e5a3f  jnz     loc_1800E586D
0x1800e5a45  xor     eax, eax
0x1800e5a47  add     rsp, 28h
0x1800e5a4b  pop     r15
0x1800e5a4d  pop     r14
0x1800e5a4f  pop     r13
0x1800e5a51  pop     r12
0x1800e5a53  pop     rdi
0x1800e5a54  pop     rsi
0x1800e5a55  pop     rbp
0x1800e5a56  pop     rbx
0x1800e5a57  retn
```
