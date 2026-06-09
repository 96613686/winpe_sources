# CEnumMediaTypes::Next(ulong,_AMMediaType * *,ulong *)

- ea: `0x180011840`
- end: `0x1800119b3`
- name: `?Next@CEnumMediaTypes@@UEAAJKPEAPEAU_AMMediaType@@PEAK@Z`
- size: `371`
- prototype: `__int64 __fastcall(CEnumMediaTypes *__hidden this, unsigned int, struct _AMMediaType **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180009c4c`
- `0x180011840`
- `0x1800119bc`
- `0x18001f620`
- `0x18001ffb0`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800118ea`
- `ole32!CoTaskMemAlloc` at `0x1800118ea`
- `ole32!CoTaskMemFree` at `0x180011995`
- `ole32!CoTaskMemFree` at `0x180011995`

## pseudocode

```c
__int64 __fastcall CEnumMediaTypes::Next(
        CEnumMediaTypes *this,
        unsigned int a2,
        struct _AMMediaType **a3,
        unsigned int *a4)
{
  struct _AMMediaType **v5; // rsi
  unsigned int v8; // r14d
  __int64 m_Position; // rdx
  CBasePin *m_pPin; // rcx
  CBasePin_vtbl *v11; // rax
  struct _AMMediaType *v12; // rax
  struct _AMMediaType v14; // [rsp+20h] [rbp-39h] BYREF

  v5 = a3;
  if ( !a3 )
    return 2147500035LL;
  if ( (unsigned int)CEnumMediaTypes::AreWeOutOfSync(this) == 1 )
    return 2147746307LL;
  if ( a4 )
  {
    *a4 = 0;
  }
  else if ( a2 > 1 )
  {
    return 2147942487LL;
  }
  v8 = 0;
  while ( a2 )
  {
    memset_0((void *)&v14, 0, sizeof(v14));
    m_Position = (unsigned int)this->m_Position;
    m_pPin = this->m_pPin;
    v14.lSampleSize = 1;
    v14.bFixedSizeSamples = 1;
    v11 = m_pPin->CUnknown::INonDelegatingUnknown::__vftable;
    this->m_Position = m_Position + 1;
    if ( v11->GetMediaType(m_pPin, m_Position, (CMediaType *)&v14) )
    {
      FreeMediaType(&v14);
      break;
    }
    v12 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
    *v5 = v12;
    if ( !v12 )
    {
      if ( v14.cbFormat )
        CoTaskMemFree(v14.pbFormat);
      break;
    }
    ++v5;
    *v12 = v14;
    ++v8;
    --a2;
  }
  if ( a4 )
    *a4 = v8;
  return a2 != 0;
}

```

## disassembly

```asm
0x180011840  mov     [rsp-8+arg_8], rbx
0x180011845  push    rbp
0x180011846  push    rsi
0x180011847  push    rdi
0x180011848  push    r14
0x18001184a  push    r15
0x18001184c  lea     rbp, [rsp-37h]
0x180011851  sub     rsp, 90h
0x180011858  mov     rax, cs:__security_cookie
0x18001185f  xor     rax, rsp
0x180011862  mov     [rbp+57h+var_30], rax
0x180011866  mov     rdi, r9
0x180011869  mov     rsi, r8
0x18001186c  mov     ebx, edx
0x18001186e  mov     r15, rcx
0x180011871  test    r8, r8
0x180011874  jz      loc_180011973
0x18001187a  call    ?AreWeOutOfSync@CEnumMediaTypes@@AEAAHXZ; CEnumMediaTypes::AreWeOutOfSync(void)
0x18001187f  cmp     eax, 1
0x180011882  jz      loc_18001198A
0x180011888  test    rdi, rdi
0x18001188b  jz      loc_18001197A
0x180011891  mov     dword ptr [rdi], 0
0x180011897  xor     r14d, r14d
0x18001189a  test    ebx, ebx
0x18001189c  jz      loc_180011943
0x1800118a2  xor     edx, edx; Val
0x1800118a4  lea     rcx, [rbp+57h+var_90]; void *
0x1800118a8  lea     r8d, [rdx+58h]; Size
0x1800118ac  call    memset_0
0x1800118b1  mov     edx, [r15+8]
0x1800118b5  mov     rcx, [r15+10h]
0x1800118b9  mov     [rbp+57h+var_90.lSampleSize], 1
0x1800118c0  mov     [rbp+57h+var_90.bFixedSizeSamples], 1
0x1800118c7  lea     r8d, [rdx+1]
0x1800118cb  mov     rax, [rcx]
0x1800118ce  mov     [r15+8], r8d
0x1800118d2  lea     r8, [rbp+57h+var_90]
0x1800118d6  mov     rax, [rax+68h]
0x1800118da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118df  test    eax, eax
0x1800118e1  jnz     loc_1800119A3
0x1800118e7  lea     ecx, [rax+58h]; cb
0x1800118ea  call    cs:__imp_CoTaskMemAlloc
0x1800118f1  nop     dword ptr [rax+rax+00h]
0x1800118f6  mov     [rsi], rax
0x1800118f9  test    rax, rax
0x1800118fc  jz      short loc_18001193D
0x1800118fe  movaps  xmm0, xmmword ptr [rbp+57h+var_90.majortype.Data1]
0x180011902  add     rsi, 8
0x180011906  movups  xmmword ptr [rax], xmm0
0x180011909  inc     r14d
0x18001190c  movaps  xmm1, xmmword ptr [rbp+57h+var_90.subtype.Data1]
0x180011910  dec     ebx
0x180011912  movups  xmmword ptr [rax+10h], xmm1
0x180011916  movaps  xmm0, xmmword ptr [rbp+57h+var_90.bFixedSizeSamples]
0x18001191a  movups  xmmword ptr [rax+20h], xmm0
0x18001191e  movaps  xmm1, xmmword ptr [rbp+57h+var_90.formattype.Data2]
0x180011922  movups  xmmword ptr [rax+30h], xmm1
0x180011926  movaps  xmm0, xmmword ptr [rbp+57h+var_90.pUnk]
0x18001192a  movups  xmmword ptr [rax+40h], xmm0
0x18001192e  movsd   xmm1, [rbp+57h+var_90.pbFormat]
0x180011933  movsd   qword ptr [rax+50h], xmm1
0x180011938  jmp     loc_18001189A
0x18001193d  cmp     [rbp+57h+var_90.cbFormat], 0
0x180011941  jnz     short loc_180011991
0x180011943  test    rdi, rdi
0x180011946  jnz     short loc_1800119AE
0x180011948  xor     eax, eax
0x18001194a  test    ebx, ebx
0x18001194c  setnz   al
0x18001194f  mov     rcx, [rbp+57h+var_30]
0x180011953  xor     rcx, rsp; StackCookie
0x180011956  call    __security_check_cookie
0x18001195b  mov     rbx, [rsp+0B0h+arg_8]
0x180011963  add     rsp, 90h
0x18001196a  pop     r15
0x18001196c  pop     r14
0x18001196e  pop     rdi
0x18001196f  pop     rsi
0x180011970  pop     rbp
0x180011971  retn
0x180011973  mov     eax, 80004003h
0x180011978  jmp     short loc_18001194F
0x18001197a  cmp     ebx, 1
0x18001197d  jbe     loc_180011897
0x180011983  mov     eax, 80070057h
0x180011988  jmp     short loc_18001194F
0x18001198a  mov     eax, 80040203h
0x18001198f  jmp     short loc_18001194F
0x180011991  mov     rcx, [rbp+57h+var_90.pbFormat]; pv
0x180011995  call    cs:__imp_CoTaskMemFree
0x18001199c  nop     dword ptr [rax+rax+00h]
0x1800119a1  jmp     short loc_180011943
0x1800119a3  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x1800119a7  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800119ac  jmp     short loc_180011943
0x1800119ae  mov     [rdi], r14d
0x1800119b1  jmp     short loc_180011948
```
