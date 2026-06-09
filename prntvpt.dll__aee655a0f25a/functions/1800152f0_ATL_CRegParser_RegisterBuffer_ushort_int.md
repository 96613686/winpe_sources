# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800152f0`
- end: `0x18001545d`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015464`

## callees

- `0x18000f970`
- `0x180014370`
- `0x18001472c`
- `0x1800152f0`
- `0x1800155fc`
- `0x180016514`
- `0x180022540`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18001538c`
- `KERNEL32!lstrcmpiW` at `0x18001538c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015433`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  __int64 v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, &pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    while ( **(_WORD **)this )
    {
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
          break;
      }
      v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
      if ( !v9 )
        goto LABEL_17;
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      if ( String1[0] != 123 )
      {
LABEL_17:
        Token = -2147352567;
        break;
      }
      if ( a3 )
      {
        v10 = *(_QWORD *)this;
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *(_QWORD *)this = v10;
          ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace(this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x1800152f0  push    rbx
0x1800152f2  push    rbp
0x1800152f3  push    rsi
0x1800152f4  push    rdi
0x1800152f5  push    r13
0x1800152f7  push    r14
0x1800152f9  push    r15
0x1800152fb  mov     eax, 2050h
0x180015300  call    _alloca_probe
0x180015305  sub     rsp, rax
0x180015308  mov     rax, cs:__security_cookie
0x18001530f  xor     rax, rsp
0x180015312  mov     [rsp+2088h+var_48], rax
0x18001531a  mov     r15d, r8d
0x18001531d  mov     [rsp+2088h+pv], 0
0x180015326  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18001532b  mov     rdi, rcx
0x18001532e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180015333  mov     ebx, eax
0x180015335  test    eax, eax
0x180015337  js      loc_18001543B
0x18001533d  mov     rbp, [rsp+2088h+pv]
0x180015342  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180015349  mov     [rdi], rbp
0x18001534c  mov     rcx, [rdi]
0x18001534f  xor     eax, eax
0x180015351  cmp     ax, [rcx]
0x180015354  jz      loc_180015430
0x18001535a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001535f  mov     rcx, rdi; this
0x180015362  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015367  mov     ebx, eax
0x180015369  test    eax, eax
0x18001536b  js      loc_180015430
0x180015371  xor     ebx, ebx
0x180015373  cmp     ebx, 0Eh
0x180015376  jnb     loc_18001542B
0x18001537c  movsxd  rsi, ebx
0x18001537f  lea     rcx, [rsp+2088h+String1]; lpString1
0x180015384  add     rsi, rsi
0x180015387  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001538c  call    cs:__imp_lstrcmpiW
0x180015392  test    eax, eax
0x180015394  jz      short loc_18001539A
0x180015396  inc     ebx
0x180015398  jmp     short loc_180015373
0x18001539a  mov     rsi, [r13+rsi*8+8]
0x18001539f  test    rsi, rsi
0x1800153a2  jz      loc_18001542B
0x1800153a8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800153ad  mov     rcx, rdi; this
0x1800153b0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800153b5  mov     ebx, eax
0x1800153b7  test    eax, eax
0x1800153b9  js      short loc_180015430
0x1800153bb  mov     eax, 7Bh ; '{'
0x1800153c0  cmp     ax, [rsp+2088h+String1]
0x1800153c5  jnz     short loc_18001542B
0x1800153c7  mov     [rsp+2088h+var_2068], 0; int
0x1800153cf  mov     r8, rsi; HKEY
0x1800153d2  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800153d7  mov     rcx, rdi; this
0x1800153da  test    r15d, r15d
0x1800153dd  jz      short loc_180015410
0x1800153df  mov     r14, [rdi]
0x1800153e2  mov     r9d, r15d; int
0x1800153e5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800153ea  mov     ebx, eax
0x1800153ec  test    eax, eax
0x1800153ee  jns     short loc_18001541E
0x1800153f0  xor     r9d, r9d; int
0x1800153f3  mov     [rdi], r14
0x1800153f6  mov     r8, rsi; HKEY
0x1800153f9  mov     [rsp+2088h+var_2068], 0; int
0x180015401  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180015406  mov     rcx, rdi; this
0x180015409  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001540e  jmp     short loc_180015430
0x180015410  xor     r9d, r9d; int
0x180015413  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180015418  mov     ebx, eax
0x18001541a  test    eax, eax
0x18001541c  js      short loc_180015430
0x18001541e  mov     rcx, rdi; this
0x180015421  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180015426  jmp     loc_18001534C
0x18001542b  mov     ebx, 80020009h
0x180015430  mov     rcx, rbp; pv
0x180015433  call    cs:__imp_CoTaskMemFree
0x180015439  mov     eax, ebx
0x18001543b  mov     rcx, [rsp+2088h+var_48]
0x180015443  xor     rcx, rsp; StackCookie
0x180015446  call    __security_check_cookie
0x18001544b  add     rsp, 2050h
0x180015452  pop     r15
0x180015454  pop     r14
0x180015456  pop     r13
0x180015458  pop     rdi
0x180015459  pop     rsi
0x18001545a  pop     rbp
0x18001545b  pop     rbx
0x18001545c  retn
```
