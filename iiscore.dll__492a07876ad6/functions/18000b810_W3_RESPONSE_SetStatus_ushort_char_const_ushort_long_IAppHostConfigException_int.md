# W3_RESPONSE::SetStatus(ushort,char const *,ushort,long,IAppHostConfigException *,int)

- ea: `0x18000b810`
- end: `0x18000bcd6`
- name: `?SetStatus@W3_RESPONSE@@QEAAJGPEBDGJPEAUIAppHostConfigException@@H@Z`
- size: `1222`
- prototype: `__int64 __fastcall(W3_RESPONSE *this, unsigned __int16, const char *, __int16, int, struct IAppHostConfigException *, int)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180005930`
- `0x180006060`
- `0x180006f10`
- `0x180007550`
- `0x180009ba0`
- `0x180009d44`
- `0x180009e50`
- `0x18000bce0`
- `0x180016340`
- `0x1800180e0`
- `0x180024b80`

## callees

- `0x180009030`
- `0x18000b810`
- `0x180027878`
- `0x180027af4`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_ultow` at `0x18000bb06`
- `msvcrt!_ultow` at `0x18000bb06`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bc4f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000bc4f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bc01`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bc01`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bb32`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000bb32`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bab7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bab7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb4e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb67`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb83`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb9d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb4e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb67`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb83`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000bb9d`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000bbb2`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000bbb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bbc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bbe7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bbc8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bbe7`

## pseudocode

```c
__int64 __fastcall W3_RESPONSE::SetStatus(
        W3_RESPONSE *this,
        unsigned __int16 a2,
        const char *a3,
        __int16 a4,
        int a5,
        struct IAppHostConfigException *a6,
        int a7)
{
  char v7; // r14
  const char *v8; // rdi
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rcx
  _BYTE *v16; // rdx
  _BYTE *v17; // rax
  __int64 v18; // rcx
  struct IAppHostConfigException *v19; // rbx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  const unsigned __int16 *Str; // rax
  __int64 v25; // r10
  struct IHttpTraceContext *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  const struct _GUID *v29; // rdx
  struct IHttpTraceContext *Data4; // rcx
  unsigned int Value[2]; // [rsp+58h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A8h] BYREF
  BSTR v33; // [rsp+68h] [rbp-A0h] BYREF
  struct IAppHostConfigException *v34; // [rsp+70h] [rbp-98h]
  _BYTE v35[64]; // [rsp+78h] [rbp-90h] BYREF
  wchar_t Buffer[32]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 v37[256]; // [rsp+F8h] [rbp-10h] BYREF

  v7 = a4;
  v34 = a6;
  v8 = a3;
  if ( !a3 )
    return 2147942487LL;
  *((_WORD *)this + 314) = a4;
  *((_QWORD *)this + 9) = dword_18003C5E4;
  *((_WORD *)this + 33) = 0;
  *((_BYTE *)this + 1550) = a7 != 0;
  *((_WORD *)this + 32) = a2;
  *((_DWORD *)this + 158) = a5;
  (*(void (__fastcall **)(_QWORD, char *, _QWORD, char *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 6) + 264LL))(
    *((_QWORD *)this + 6),
    (char *)this + 636,
    0,
    (char *)this + 640,
    0,
    0,
    0);
  v11 = *((_QWORD *)this + 6);
  if ( *(_BYTE *)(v11 + 9098) )
  {
    v21 = v11 + 8;
    if ( !v11 )
      v21 = 0;
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v21, 256, 4) )
      goto LABEL_28;
    if ( a2 >= 0x190u )
    {
      v22 = *((_QWORD *)this + 6);
      v23 = v22 + 8;
      if ( !v22 )
        v23 = 0;
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v23, 256, 3) )
      {
LABEL_28:
        if ( a2 < 0x190u )
        {
          v27 = *((_QWORD *)this + 6);
          v28 = v27 + 8;
          if ( !v27 )
            v28 = 0;
          if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v28, 256, 4) )
          {
            v29 = (const struct _GUID *)*((_QWORD *)this + 6);
            Data4 = (struct IHttpTraceContext *)v29->Data4;
            if ( !v29 )
              Data4 = 0;
            IISRequestNotificationEvents::MODULE_SET_RESPONSE_SUCCESS_STATUS::RaiseEvent(
              Data4,
              v29,
              *((const unsigned __int16 **)this + 80),
              *((_DWORD *)this + 159),
              a2,
              v8);
          }
        }
        else
        {
          bstrString = 0;
          Value[0] = 0;
          memset_0(Buffer, 0, sizeof(Buffer));
          v33 = 0;
          memset_0(v37, 0, sizeof(v37));
          STRU::STRU((STRU *)v35, v37, 0x100u);
          if ( v34 )
          {
            ((void (__fastcall *)(struct IAppHostConfigException *, BSTR *))v34->lpVtbl->get_ErrorString)(
              v34,
              &bstrString);
            ((void (__fastcall *)(struct IAppHostConfigException *, unsigned int *))v34->lpVtbl->get_LineNumber)(
              v34,
              Value);
            _ultow(Value[0], Buffer, 10);
            ((void (__fastcall *)(struct IAppHostConfigException *, BSTR *))v34->lpVtbl->get_FileName)(v34, &v33);
            if ( (int)STRU::Copy((STRU *)v35, v33) < 0
              || (int)STRU::Append((STRU *)v35, L" ( ") < 0
              || (int)STRU::Append((STRU *)v35, Buffer) < 0
              || (int)STRU::Append((STRU *)v35, L") :") < 0
              || (int)STRU::Append((STRU *)v35, bstrString) < 0 )
            {
              STRU::Reset((STRU *)v35);
            }
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v33 )
            {
              SysFreeString(v33);
              v33 = 0;
            }
          }
          Str = STRU::QueryStr((STRU *)v35);
          v25 = *((_QWORD *)this + 6);
          v26 = (struct IHttpTraceContext *)(v25 + 8);
          if ( !v25 )
            v26 = 0;
          IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::RaiseEvent(
            v26,
            0,
            *((const unsigned __int16 **)this + 80),
            *((_DWORD *)this + 159),
            a2,
            v8,
            v7,
            a5,
            Str);
          STRU::~STRU((STRU *)v35);
        }
      }
    }
  }
  v12 = -1;
  do
    ++v12;
  while ( v8[v12] );
  if ( (unsigned int)v12 > 0xFFFF )
    return 2147942413LL;
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 144LL))(
          *((_QWORD *)this + 6),
          (unsigned int)(v12 + 1));
  if ( !v13 )
    return 2147942408LL;
  v14 = (unsigned int)(v12 + 1);
  v15 = 2147483646;
  v16 = (_BYTE *)v13;
  do
  {
    if ( !v15 )
      break;
    if ( !*v8 )
      break;
    *v16++ = *v8++;
    --v15;
    --v14;
  }
  while ( v14 );
  v17 = v16 - 1;
  if ( v14 )
    v17 = v16;
  *v17 = 0;
  v18 = *((_QWORD *)this + 81);
  *((_QWORD *)this + 9) = v13;
  *((_WORD *)this + 33) = v12;
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)this + 81) = 0;
  }
  v19 = v34;
  if ( v34 )
  {
    ((void (__fastcall *)(struct IAppHostConfigException *))v34->lpVtbl->AddRef)(v34);
    *((_QWORD *)this + 81) = v19;
  }
  return 0;
}

```

## disassembly

```asm
0x18000b810  mov     r11, rsp
0x18000b813  push    rbp
0x18000b814  push    rbx
0x18000b815  push    rsi
0x18000b816  push    rdi
0x18000b817  push    r14
0x18000b819  lea     rbp, [r11-238h]
0x18000b820  sub     rsp, 310h
0x18000b827  mov     rax, cs:__security_cookie
0x18000b82e  xor     rax, rsp
0x18000b831  mov     [rbp+230h+var_40], rax
0x18000b838  mov     rax, [rbp+230h+arg_28]
0x18000b83f  movzx   r14d, r9w
0x18000b843  mov     [rsp+330h+var_2C8], rax
0x18000b848  mov     rdi, r8
0x18000b84b  movzx   ebx, dx
0x18000b84e  mov     rsi, rcx
0x18000b851  test    r8, r8
0x18000b854  jz      loc_18000B9FF
0x18000b85a  xor     edx, edx
0x18000b85c  mov     [rcx+274h], r9w
0x18000b864  cmp     [rbp+230h+arg_30], edx
0x18000b86a  lea     rax, dword_18003C5E4
0x18000b871  mov     [rcx+48h], rax
0x18000b875  lea     r9, [rsi+280h]
0x18000b87c  setnz   al
0x18000b87f  mov     [rcx+42h], dx
0x18000b883  mov     [rcx+60Eh], al
0x18000b889  xor     r8d, r8d
0x18000b88c  mov     qword ptr [rsp+330h+var_300], rdx
0x18000b891  mov     [r11+10h], r12
0x18000b895  mov     [r11-30h], r13
0x18000b899  mov     r13d, dword ptr [rbp+230h+arg_20]
0x18000b8a0  mov     [rcx+40h], bx
0x18000b8a4  mov     [rcx+278h], r13d
0x18000b8ab  mov     rcx, [rcx+30h]
0x18000b8af  mov     [rsp+330h+var_308], rdx
0x18000b8b4  mov     qword ptr [rsp+330h+var_310], rdx
0x18000b8b9  lea     rdx, [rsi+27Ch]
0x18000b8c0  mov     [r11-38h], r15
0x18000b8c4  mov     rax, [rcx]
0x18000b8c7  mov     rax, [rax+108h]
0x18000b8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8d3  mov     rdx, [rsi+30h]
0x18000b8d7  cmp     byte ptr [rdx+238Ah], 0
0x18000b8de  jnz     loc_18000BA06
0x18000b8e4  mov     r15, [rsp+330h+var_30]
0x18000b8ec  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b8f3  mov     r13, [rsp+308h]
0x18000b8fb  mov     r12, [rsp+330h+arg_8]
0x18000b903  inc     rbx
0x18000b906  cmp     byte ptr [rdi+rbx], 0
0x18000b90a  jnz     short loc_18000B903
0x18000b90c  cmp     ebx, 0FFFFh
0x18000b912  ja      loc_18000B9B1
0x18000b918  mov     rcx, [rsi+30h]
0x18000b91c  lea     r14d, [rbx+1]
0x18000b920  mov     edx, r14d
0x18000b923  mov     rax, [rcx]
0x18000b926  mov     rax, [rax+90h]
0x18000b92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b932  mov     r9, rax
0x18000b935  test    rax, rax
0x18000b938  jz      loc_18000B9D4
0x18000b93e  lea     eax, [r14-1]
0x18000b942  mov     r8d, r14d
0x18000b945  mov     ecx, 7FFFFFFEh
0x18000b94a  cmp     eax, ecx
0x18000b94c  ja      loc_18000B9F4
0x18000b952  mov     rdx, r9
0x18000b955  test    r14d, r14d
0x18000b958  jz      short loc_18000B97D
0x18000b95a  nop     word ptr [rax+rax+00h]
0x18000b960  test    rcx, rcx
0x18000b963  jz      short loc_18000B97D
0x18000b965  movzx   eax, byte ptr [rdi]
0x18000b968  test    al, al
0x18000b96a  jz      short loc_18000B97D
0x18000b96c  mov     [rdx], al
0x18000b96e  inc     rdi
0x18000b971  inc     rdx
0x18000b974  dec     rcx
0x18000b977  sub     r8, 1
0x18000b97b  jnz     short loc_18000B960
0x18000b97d  test    r8, r8
0x18000b980  lea     rax, [rdx-1]
0x18000b984  cmovnz  rax, rdx
0x18000b988  mov     byte ptr [rax], 0
0x18000b98b  mov     rcx, [rsi+288h]
0x18000b992  mov     [rsi+48h], r9
0x18000b996  mov     [rsi+42h], bx
0x18000b99a  test    rcx, rcx
0x18000b99d  jnz     short loc_18000B9DB
0x18000b99f  mov     rbx, [rsp+330h+var_2C8]
0x18000b9a4  test    rbx, rbx
0x18000b9a7  jnz     loc_18000BCBB
0x18000b9ad  xor     eax, eax
0x18000b9af  jmp     short loc_18000B9B6
0x18000b9b1  mov     eax, 8007000Dh
0x18000b9b6  mov     rcx, [rbp+230h+var_40]
0x18000b9bd  xor     rcx, rsp; StackCookie
0x18000b9c0  call    __security_check_cookie
0x18000b9c5  add     rsp, 310h
0x18000b9cc  pop     r14
0x18000b9ce  pop     rdi
0x18000b9cf  pop     rsi
0x18000b9d0  pop     rbx
0x18000b9d1  pop     rbp
0x18000b9d2  retn
0x18000b9d4  mov     eax, 80070008h
0x18000b9d9  jmp     short loc_18000B9B6
0x18000b9db  mov     rax, [rcx]
0x18000b9de  mov     rax, [rax+10h]
0x18000b9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e7  mov     qword ptr [rsi+288h], 0
0x18000b9f2  jmp     short loc_18000B99F
0x18000b9f4  test    r14d, r14d
0x18000b9f7  jz      short loc_18000B98B
0x18000b9f9  mov     byte ptr [r9], 0
0x18000b9fd  jmp     short loc_18000B98B
0x18000b9ff  mov     eax, 80070057h
0x18000ba04  jmp     short loc_18000B9B6
0x18000ba06  xor     eax, eax
0x18000ba08  lea     rcx, [rdx+8]
0x18000ba0c  test    rdx, rdx
0x18000ba0f  mov     r8d, 4
0x18000ba15  mov     edx, 100h
0x18000ba1a  cmovz   rcx, rax
0x18000ba1e  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000ba23  mov     ecx, 190h
0x18000ba28  test    eax, eax
0x18000ba2a  jnz     short loc_18000BA63
0x18000ba2c  cmp     bx, cx
0x18000ba2f  jb      loc_18000B8E4
0x18000ba35  mov     rdx, [rsi+30h]
0x18000ba39  xor     eax, eax
0x18000ba3b  test    rdx, rdx
0x18000ba3e  mov     r8d, 3
0x18000ba44  lea     rcx, [rdx+8]
0x18000ba48  mov     edx, 100h
0x18000ba4d  cmovz   rcx, rax
0x18000ba51  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000ba56  test    eax, eax
0x18000ba58  jz      loc_18000B8E4
0x18000ba5e  mov     ecx, 190h
0x18000ba63  cmp     bx, cx
0x18000ba66  jb      loc_18000BC60
0x18000ba6c  xor     edx, edx; Val
0x18000ba6e  mov     [rsp+330h+bstrString], 0
0x18000ba77  mov     r8d, 40h ; '@'; Size
0x18000ba7d  mov     [rsp+330h+Value], 0
0x18000ba85  lea     rcx, [rbp+230h+Buffer]; void *
0x18000ba89  call    memset_0
0x18000ba8e  xor     edx, edx; Val
0x18000ba90  mov     [rsp+330h+var_2D0], 0
0x18000ba99  mov     r8d, 200h; Size
0x18000ba9f  lea     rcx, [rbp+230h+var_240]; void *
0x18000baa3  call    memset_0
0x18000baa8  mov     r8d, 100h
0x18000baae  lea     rdx, [rbp+230h+var_240]
0x18000bab2  lea     rcx, [rsp+70h]
0x18000bab7  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000babe  nop     dword ptr [rax+rax+00h]
0x18000bac3  mov     rcx, [rsp+330h+var_2C8]
0x18000bac8  test    rcx, rcx
0x18000bacb  jz      loc_18000BBFC
0x18000bad1  mov     rax, [rcx]
0x18000bad4  lea     rdx, [rsp+330h+bstrString]
0x18000bad9  mov     rax, [rax+48h]
0x18000badd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae2  mov     rcx, [rsp+330h+var_2C8]
0x18000bae7  lea     rdx, [rsp+330h+Value]
0x18000baec  mov     rax, [rcx]
0x18000baef  mov     rax, [rax+18h]
0x18000baf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf8  mov     ecx, [rsp+330h+Value]; Value
0x18000bafc  lea     rdx, [rbp+230h+Buffer]; Buffer
0x18000bb00  mov     r8d, 0Ah; Radix
0x18000bb06  call    cs:__imp__ultow
0x18000bb0d  nop     dword ptr [rax+rax+00h]
0x18000bb12  mov     rcx, [rsp+330h+var_2C8]
0x18000bb17  lea     rdx, [rsp+330h+var_2D0]
0x18000bb1c  mov     rax, [rcx]
0x18000bb1f  mov     rax, [rax+20h]
0x18000bb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb28  mov     rdx, [rsp+330h+var_2D0]
0x18000bb2d  lea     rcx, [rsp+70h]
0x18000bb32  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000bb39  nop     dword ptr [rax+rax+00h]
0x18000bb3e  test    eax, eax
0x18000bb40  js      short loc_18000BBAD
0x18000bb42  lea     rdx, asc_18003E1C0; " ( "
0x18000bb49  lea     rcx, [rsp+70h]
0x18000bb4e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bb55  nop     dword ptr [rax+rax+00h]
0x18000bb5a  test    eax, eax
0x18000bb5c  js      short loc_18000BBAD
0x18000bb5e  lea     rdx, [rbp+230h+Buffer]
0x18000bb62  lea     rcx, [rsp+70h]
0x18000bb67  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bb6e  nop     dword ptr [rax+rax+00h]
0x18000bb73  test    eax, eax
0x18000bb75  js      short loc_18000BBAD
0x18000bb77  lea     rdx, asc_18003E1C8; ") :"
0x18000bb7e  lea     rcx, [rsp+70h]
0x18000bb83  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bb8a  nop     dword ptr [rax+rax+00h]
0x18000bb8f  test    eax, eax
0x18000bb91  js      short loc_18000BBAD
0x18000bb93  mov     rdx, [rsp+330h+bstrString]
0x18000bb98  lea     rcx, [rsp+70h]
0x18000bb9d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000bba4  nop     dword ptr [rax+rax+00h]
0x18000bba9  test    eax, eax
0x18000bbab  jns     short loc_18000BBBE
0x18000bbad  lea     rcx, [rsp+70h]
0x18000bbb2  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000bbb9  nop     dword ptr [rax+rax+00h]
0x18000bbbe  mov     rcx, [rsp+330h+bstrString]; bstrString
0x18000bbc3  test    rcx, rcx
0x18000bbc6  jz      short loc_18000BBDD
0x18000bbc8  call    cs:__imp_SysFreeString
0x18000bbcf  nop     dword ptr [rax+rax+00h]
0x18000bbd4  mov     [rsp+330h+bstrString], 0
0x18000bbdd  mov     rcx, [rsp+330h+var_2D0]; bstrString
0x18000bbe2  test    rcx, rcx
0x18000bbe5  jz      short loc_18000BBFC
0x18000bbe7  call    cs:__imp_SysFreeString
0x18000bbee  nop     dword ptr [rax+rax+00h]
0x18000bbf3  mov     [rsp+330h+var_2D0], 0
0x18000bbfc  lea     rcx, [rsp+70h]
0x18000bc01  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bc08  nop     dword ptr [rax+rax+00h]
0x18000bc0d  mov     r10, [rsi+30h]
0x18000bc11  xor     edx, edx; struct _GUID *
0x18000bc13  mov     r9d, [rsi+27Ch]; unsigned int
0x18000bc1a  test    r10, r10
0x18000bc1d  mov     r8, [rsi+280h]; unsigned __int16 *
0x18000bc24  mov     [rsp+40h], rax; unsigned __int16 *
0x18000bc29  mov     dword ptr [rsp+330h+var_2F8], r13d; char
0x18000bc2e  lea     rcx, [r10+8]
0x18000bc32  mov     word ptr [rsp+330h+var_300], r14w; char
0x18000bc38  cmovz   rcx, rdx; struct IHttpTraceContext *
0x18000bc3c  mov     [rsp+330h+var_308], rdi; char *
0x18000bc41  mov     dword ptr [rsp+330h+var_310], ebx; char
0x18000bc45  call    ?RaiseEvent@MODULE_SET_RESPONSE_ERROR_STATUS@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGKKPEBDGK2@Z; IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ulong,ulong,char const *,ushort,ulong,ushort const *)
0x18000bc4a  lea     rcx, [rsp+70h]
0x18000bc4f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000bc56  nop     dword ptr [rax+rax+00h]
0x18000bc5b  jmp     loc_18000B8E4
0x18000bc60  mov     rdx, [rsi+30h]
0x18000bc64  xor     eax, eax
0x18000bc66  test    rdx, rdx
0x18000bc69  mov     r8d, 4
0x18000bc6f  lea     rcx, [rdx+8]
0x18000bc73  mov     edx, 100h
0x18000bc78  cmovz   rcx, rax
0x18000bc7c  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000bc81  test    eax, eax
0x18000bc83  jz      loc_18000B8E4
0x18000bc89  mov     rdx, [rsi+30h]; struct _GUID *
0x18000bc8d  xor     eax, eax
0x18000bc8f  mov     r9d, [rsi+27Ch]; unsigned int
0x18000bc96  test    rdx, rdx
0x18000bc99  mov     r8, [rsi+280h]; unsigned __int16 *
0x18000bca0  mov     [rsp+330h+var_308], rdi; char *
0x18000bca5  lea     rcx, [rdx+8]
0x18000bca9  mov     dword ptr [rsp+330h+var_310], ebx; char
0x18000bcad  cmovz   rcx, rax; struct IHttpTraceContext *
0x18000bcb1  call    ?RaiseEvent@MODULE_SET_RESPONSE_SUCCESS_STATUS@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGKKPEBD@Z; IISRequestNotificationEvents::MODULE_SET_RESPONSE_SUCCESS_STATUS::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ulong,ulong,char const *)
0x18000bcb6  jmp     loc_18000B8E4
0x18000bcbb  mov     rax, [rbx]
0x18000bcbe  mov     rcx, rbx
0x18000bcc1  mov     rax, [rax+8]
0x18000bcc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcca  mov     [rsi+288h], rbx
0x18000bcd1  jmp     loc_18000B9AD
```
