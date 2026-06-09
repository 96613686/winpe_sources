# W3_RESPONSE::SetStatus(ushort,char const *,ushort,long,IAppHostConfigException *,int)

- ea: `0x18000d340`
- end: `0x18000d7bd`
- name: `?SetStatus@W3_RESPONSE@@QEAAJGPEBDGJPEAUIAppHostConfigException@@H@Z`
- size: `1149`
- prototype: `int(W3_RESPONSE *__hidden this, unsigned __int16, const char *, unsigned __int16, int, struct IAppHostConfigException *, int)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800054d0`
- `0x180005bf0`
- `0x180006a70`
- `0x1800070a0`
- `0x1800094c4`
- `0x1800095d0`
- `0x18000aed0`
- `0x18000d7c4`
- `0x18000dd80`
- `0x180015120`
- `0x180022e70`

## callees

- `0x180008930`
- `0x18000d340`
- `0x18002589c`
- `0x180025b18`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_ultow` at `0x18000d62f`
- `msvcrt!_ultow` at `0x18000d62f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d73c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000d73c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6f4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000d6f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d655`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000d655`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d5e6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d5e6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d66b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d67e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d694`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d6a8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d66b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d67e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d694`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000d6a8`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000d6b7`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x18000d6b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d6c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d6e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d6c7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d6e0`

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
  *((_QWORD *)this + 9) = dword_1800395E4;
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
0x18000d340  mov     r11, rsp
0x18000d343  push    rbp
0x18000d344  push    rbx
0x18000d345  push    rsi
0x18000d346  push    rdi
0x18000d347  push    r14
0x18000d349  lea     rbp, [r11-238h]
0x18000d350  sub     rsp, 310h
0x18000d357  mov     rax, cs:__security_cookie
0x18000d35e  xor     rax, rsp
0x18000d361  mov     [rbp+230h+var_40], rax
0x18000d368  mov     rax, [rbp+230h+arg_28]
0x18000d36f  movzx   r14d, r9w
0x18000d373  mov     [rsp+330h+var_2C8], rax
0x18000d378  mov     rdi, r8
0x18000d37b  movzx   ebx, dx
0x18000d37e  mov     rsi, rcx
0x18000d381  test    r8, r8
0x18000d384  jz      loc_18000D52E
0x18000d38a  xor     edx, edx
0x18000d38c  mov     [rcx+274h], r9w
0x18000d394  cmp     [rbp+230h+arg_30], edx
0x18000d39a  lea     rax, dword_1800395E4
0x18000d3a1  mov     [rcx+48h], rax
0x18000d3a5  lea     r9, [rsi+280h]
0x18000d3ac  setnz   al
0x18000d3af  mov     [rcx+42h], dx
0x18000d3b3  mov     [rcx+60Eh], al
0x18000d3b9  xor     r8d, r8d
0x18000d3bc  mov     qword ptr [rsp+330h+var_300], rdx
0x18000d3c1  mov     [r11+10h], r12
0x18000d3c5  mov     [r11-30h], r13
0x18000d3c9  mov     r13d, dword ptr [rbp+230h+arg_20]
0x18000d3d0  mov     [rcx+40h], bx
0x18000d3d4  mov     [rcx+278h], r13d
0x18000d3db  mov     rcx, [rcx+30h]
0x18000d3df  mov     [rsp+330h+var_308], rdx
0x18000d3e4  mov     qword ptr [rsp+330h+var_310], rdx
0x18000d3e9  lea     rdx, [rsi+27Ch]
0x18000d3f0  mov     [r11-38h], r15
0x18000d3f4  mov     rax, [rcx]
0x18000d3f7  mov     rax, [rax+108h]
0x18000d3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d403  mov     rdx, [rsi+30h]
0x18000d407  cmp     byte ptr [rdx+238Ah], 0
0x18000d40e  jnz     loc_18000D535
0x18000d414  mov     r15, [rsp+330h+var_30]
0x18000d41c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000d423  mov     r13, [rsp+308h]
0x18000d42b  mov     r12, [rsp+330h+arg_8]
0x18000d433  inc     rbx
0x18000d436  cmp     byte ptr [rdi+rbx], 0
0x18000d43a  jnz     short loc_18000D433
0x18000d43c  cmp     ebx, 0FFFFh
0x18000d442  ja      loc_18000D4E1
0x18000d448  mov     rcx, [rsi+30h]
0x18000d44c  lea     r14d, [rbx+1]
0x18000d450  mov     edx, r14d
0x18000d453  mov     rax, [rcx]
0x18000d456  mov     rax, [rax+90h]
0x18000d45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d462  mov     r9, rax
0x18000d465  test    rax, rax
0x18000d468  jz      loc_18000D503
0x18000d46e  lea     eax, [r14-1]
0x18000d472  mov     r8d, r14d
0x18000d475  mov     ecx, 7FFFFFFEh
0x18000d47a  cmp     eax, ecx
0x18000d47c  ja      loc_18000D523
0x18000d482  mov     rdx, r9
0x18000d485  test    r14d, r14d
0x18000d488  jz      short loc_18000D4AD
0x18000d48a  nop     word ptr [rax+rax+00h]
0x18000d490  test    rcx, rcx
0x18000d493  jz      short loc_18000D4AD
0x18000d495  movzx   eax, byte ptr [rdi]
0x18000d498  test    al, al
0x18000d49a  jz      short loc_18000D4AD
0x18000d49c  mov     [rdx], al
0x18000d49e  inc     rdi
0x18000d4a1  inc     rdx
0x18000d4a4  dec     rcx
0x18000d4a7  sub     r8, 1
0x18000d4ab  jnz     short loc_18000D490
0x18000d4ad  test    r8, r8
0x18000d4b0  lea     rax, [rdx-1]
0x18000d4b4  cmovnz  rax, rdx
0x18000d4b8  mov     byte ptr [rax], 0
0x18000d4bb  mov     rcx, [rsi+288h]
0x18000d4c2  mov     [rsi+48h], r9
0x18000d4c6  mov     [rsi+42h], bx
0x18000d4ca  test    rcx, rcx
0x18000d4cd  jnz     short loc_18000D50A
0x18000d4cf  mov     rbx, [rsp+330h+var_2C8]
0x18000d4d4  test    rbx, rbx
0x18000d4d7  jnz     loc_18000D7A2
0x18000d4dd  xor     eax, eax
0x18000d4df  jmp     short loc_18000D4E6
0x18000d4e1  mov     eax, 8007000Dh
0x18000d4e6  mov     rcx, [rbp+230h+var_40]
0x18000d4ed  xor     rcx, rsp; StackCookie
0x18000d4f0  call    __security_check_cookie
0x18000d4f5  add     rsp, 310h
0x18000d4fc  pop     r14
0x18000d4fe  pop     rdi
0x18000d4ff  pop     rsi
0x18000d500  pop     rbx
0x18000d501  pop     rbp
0x18000d502  retn
0x18000d503  mov     eax, 80070008h
0x18000d508  jmp     short loc_18000D4E6
0x18000d50a  mov     rax, [rcx]
0x18000d50d  mov     rax, [rax+10h]
0x18000d511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d516  mov     qword ptr [rsi+288h], 0
0x18000d521  jmp     short loc_18000D4CF
0x18000d523  test    r14d, r14d
0x18000d526  jz      short loc_18000D4BB
0x18000d528  mov     byte ptr [r9], 0
0x18000d52c  jmp     short loc_18000D4BB
0x18000d52e  mov     eax, 80070057h
0x18000d533  jmp     short loc_18000D4E6
0x18000d535  xor     eax, eax
0x18000d537  lea     rcx, [rdx+8]
0x18000d53b  test    rdx, rdx
0x18000d53e  mov     r8d, 4
0x18000d544  mov     edx, 100h
0x18000d549  cmovz   rcx, rax
0x18000d54d  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000d552  mov     ecx, 190h
0x18000d557  test    eax, eax
0x18000d559  jnz     short loc_18000D592
0x18000d55b  cmp     bx, cx
0x18000d55e  jb      loc_18000D414
0x18000d564  mov     rdx, [rsi+30h]
0x18000d568  xor     eax, eax
0x18000d56a  test    rdx, rdx
0x18000d56d  mov     r8d, 3
0x18000d573  lea     rcx, [rdx+8]
0x18000d577  mov     edx, 100h
0x18000d57c  cmovz   rcx, rax
0x18000d580  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000d585  test    eax, eax
0x18000d587  jz      loc_18000D414
0x18000d58d  mov     ecx, 190h
0x18000d592  cmp     bx, cx
0x18000d595  jb      loc_18000D747
0x18000d59b  xor     edx, edx; Val
0x18000d59d  mov     [rsp+330h+bstrString], 0
0x18000d5a6  mov     r8d, 40h ; '@'; Size
0x18000d5ac  mov     [rsp+330h+Value], 0
0x18000d5b4  lea     rcx, [rbp+230h+Buffer]; void *
0x18000d5b8  call    memset_0
0x18000d5bd  xor     edx, edx; Val
0x18000d5bf  mov     [rsp+330h+var_2D0], 0
0x18000d5c8  mov     r8d, 200h; Size
0x18000d5ce  lea     rcx, [rbp+230h+var_240]; void *
0x18000d5d2  call    memset_0
0x18000d5d7  mov     r8d, 100h
0x18000d5dd  lea     rdx, [rbp+230h+var_240]
0x18000d5e1  lea     rcx, [rsp+70h]
0x18000d5e6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d5ec  mov     rcx, [rsp+330h+var_2C8]
0x18000d5f1  test    rcx, rcx
0x18000d5f4  jz      loc_18000D6EF
0x18000d5fa  mov     rax, [rcx]
0x18000d5fd  lea     rdx, [rsp+330h+bstrString]
0x18000d602  mov     rax, [rax+48h]
0x18000d606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60b  mov     rcx, [rsp+330h+var_2C8]
0x18000d610  lea     rdx, [rsp+330h+Value]
0x18000d615  mov     rax, [rcx]
0x18000d618  mov     rax, [rax+18h]
0x18000d61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d621  mov     ecx, [rsp+330h+Value]; Value
0x18000d625  lea     rdx, [rbp+230h+Buffer]; Buffer
0x18000d629  mov     r8d, 0Ah; Radix
0x18000d62f  call    cs:__imp__ultow
0x18000d635  mov     rcx, [rsp+330h+var_2C8]
0x18000d63a  lea     rdx, [rsp+330h+var_2D0]
0x18000d63f  mov     rax, [rcx]
0x18000d642  mov     rax, [rax+20h]
0x18000d646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d64b  mov     rdx, [rsp+330h+var_2D0]
0x18000d650  lea     rcx, [rsp+70h]
0x18000d655  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000d65b  test    eax, eax
0x18000d65d  js      short loc_18000D6B2
0x18000d65f  lea     rdx, asc_18003B1C0; " ( "
0x18000d666  lea     rcx, [rsp+70h]
0x18000d66b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d671  test    eax, eax
0x18000d673  js      short loc_18000D6B2
0x18000d675  lea     rdx, [rbp+230h+Buffer]
0x18000d679  lea     rcx, [rsp+70h]
0x18000d67e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d684  test    eax, eax
0x18000d686  js      short loc_18000D6B2
0x18000d688  lea     rdx, asc_18003B1C8; ") :"
0x18000d68f  lea     rcx, [rsp+70h]
0x18000d694  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d69a  test    eax, eax
0x18000d69c  js      short loc_18000D6B2
0x18000d69e  mov     rdx, [rsp+330h+bstrString]
0x18000d6a3  lea     rcx, [rsp+70h]
0x18000d6a8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000d6ae  test    eax, eax
0x18000d6b0  jns     short loc_18000D6BD
0x18000d6b2  lea     rcx, [rsp+70h]
0x18000d6b7  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18000d6bd  mov     rcx, [rsp+330h+bstrString]; bstrString
0x18000d6c2  test    rcx, rcx
0x18000d6c5  jz      short loc_18000D6D6
0x18000d6c7  call    cs:__imp_SysFreeString
0x18000d6cd  mov     [rsp+330h+bstrString], 0
0x18000d6d6  mov     rcx, [rsp+330h+var_2D0]; bstrString
0x18000d6db  test    rcx, rcx
0x18000d6de  jz      short loc_18000D6EF
0x18000d6e0  call    cs:__imp_SysFreeString
0x18000d6e6  mov     [rsp+330h+var_2D0], 0
0x18000d6ef  lea     rcx, [rsp+70h]
0x18000d6f4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000d6fa  mov     r10, [rsi+30h]
0x18000d6fe  xor     edx, edx; struct _GUID *
0x18000d700  mov     r9d, [rsi+27Ch]; unsigned int
0x18000d707  test    r10, r10
0x18000d70a  mov     r8, [rsi+280h]; unsigned __int16 *
0x18000d711  mov     [rsp+40h], rax; unsigned __int16 *
0x18000d716  mov     dword ptr [rsp+330h+var_2F8], r13d; char
0x18000d71b  lea     rcx, [r10+8]
0x18000d71f  mov     word ptr [rsp+330h+var_300], r14w; char
0x18000d725  cmovz   rcx, rdx; struct IHttpTraceContext *
0x18000d729  mov     [rsp+330h+var_308], rdi; char *
0x18000d72e  mov     dword ptr [rsp+330h+var_310], ebx; char
0x18000d732  call    ?RaiseEvent@MODULE_SET_RESPONSE_ERROR_STATUS@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGKKPEBDGK2@Z; IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ulong,ulong,char const *,ushort,ulong,ushort const *)
0x18000d737  lea     rcx, [rsp+70h]
0x18000d73c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000d742  jmp     loc_18000D414
0x18000d747  mov     rdx, [rsi+30h]
0x18000d74b  xor     eax, eax
0x18000d74d  test    rdx, rdx
0x18000d750  mov     r8d, 4
0x18000d756  lea     rcx, [rdx+8]
0x18000d75a  mov     edx, 100h
0x18000d75f  cmovz   rcx, rax
0x18000d763  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18000d768  test    eax, eax
0x18000d76a  jz      loc_18000D414
0x18000d770  mov     rdx, [rsi+30h]; struct _GUID *
0x18000d774  xor     eax, eax
0x18000d776  mov     r9d, [rsi+27Ch]; unsigned int
0x18000d77d  test    rdx, rdx
0x18000d780  mov     r8, [rsi+280h]; unsigned __int16 *
0x18000d787  mov     [rsp+330h+var_308], rdi; char *
0x18000d78c  lea     rcx, [rdx+8]
0x18000d790  mov     dword ptr [rsp+330h+var_310], ebx; char
0x18000d794  cmovz   rcx, rax; struct IHttpTraceContext *
0x18000d798  call    ?RaiseEvent@MODULE_SET_RESPONSE_SUCCESS_STATUS@IISRequestNotificationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBGKKPEBD@Z; IISRequestNotificationEvents::MODULE_SET_RESPONSE_SUCCESS_STATUS::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ulong,ulong,char const *)
0x18000d79d  jmp     loc_18000D414
0x18000d7a2  mov     rax, [rbx]
0x18000d7a5  mov     rcx, rbx
0x18000d7a8  mov     rax, [rax+8]
0x18000d7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7b1  mov     [rsi+288h], rbx
0x18000d7b8  jmp     loc_18000D4DD
```
