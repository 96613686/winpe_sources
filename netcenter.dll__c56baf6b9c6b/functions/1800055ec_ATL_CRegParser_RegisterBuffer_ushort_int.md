# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800055ec`
- end: `0x180005759`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005760`

## callees

- `0x180002270`
- `0x180005030`
- `0x1800051e8`
- `0x1800055ec`
- `0x180005910`
- `0x180006004`
- `0x180022330`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000572f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000572f`
- `KERNEL32!lstrcmpiW` at `0x180005688`
- `KERNEL32!lstrcmpiW` at `0x180005688`

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
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
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
0x1800055ec  push    rbx
0x1800055ee  push    rbp
0x1800055ef  push    rsi
0x1800055f0  push    rdi
0x1800055f1  push    r13
0x1800055f3  push    r14
0x1800055f5  push    r15
0x1800055f7  mov     eax, 2050h
0x1800055fc  call    _alloca_probe
0x180005601  sub     rsp, rax
0x180005604  mov     rax, cs:__security_cookie
0x18000560b  xor     rax, rsp
0x18000560e  mov     [rsp+2088h+var_48], rax
0x180005616  mov     r15d, r8d
0x180005619  mov     [rsp+2088h+pv], 0
0x180005622  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180005627  mov     rdi, rcx
0x18000562a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000562f  mov     ebx, eax
0x180005631  test    eax, eax
0x180005633  js      loc_180005737
0x180005639  mov     rbp, [rsp+2088h+pv]
0x18000563e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180005645  mov     [rdi], rbp
0x180005648  mov     rcx, [rdi]
0x18000564b  xor     eax, eax
0x18000564d  cmp     ax, [rcx]
0x180005650  jz      loc_18000572C
0x180005656  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000565b  mov     rcx, rdi; this
0x18000565e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005663  mov     ebx, eax
0x180005665  test    eax, eax
0x180005667  js      loc_18000572C
0x18000566d  xor     ebx, ebx
0x18000566f  cmp     ebx, 0Eh
0x180005672  jnb     loc_180005727
0x180005678  movsxd  rsi, ebx
0x18000567b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180005680  add     rsi, rsi
0x180005683  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005688  call    cs:__imp_lstrcmpiW
0x18000568e  test    eax, eax
0x180005690  jz      short loc_180005696
0x180005692  inc     ebx
0x180005694  jmp     short loc_18000566F
0x180005696  mov     rsi, [r13+rsi*8+8]
0x18000569b  test    rsi, rsi
0x18000569e  jz      loc_180005727
0x1800056a4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800056a9  mov     rcx, rdi; this
0x1800056ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800056b1  mov     ebx, eax
0x1800056b3  test    eax, eax
0x1800056b5  js      short loc_18000572C
0x1800056b7  mov     eax, 7Bh ; '{'
0x1800056bc  cmp     ax, [rsp+2088h+String1]
0x1800056c1  jnz     short loc_180005727
0x1800056c3  mov     [rsp+2088h+var_2068], 0; int
0x1800056cb  mov     r8, rsi; HKEY
0x1800056ce  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800056d3  mov     rcx, rdi; this
0x1800056d6  test    r15d, r15d
0x1800056d9  jz      short loc_18000570C
0x1800056db  mov     r14, [rdi]
0x1800056de  mov     r9d, r15d; int
0x1800056e1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800056e6  mov     ebx, eax
0x1800056e8  test    eax, eax
0x1800056ea  jns     short loc_18000571A
0x1800056ec  xor     r9d, r9d; int
0x1800056ef  mov     [rdi], r14
0x1800056f2  mov     r8, rsi; HKEY
0x1800056f5  mov     [rsp+2088h+var_2068], 0; int
0x1800056fd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005702  mov     rcx, rdi; this
0x180005705  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000570a  jmp     short loc_18000572C
0x18000570c  xor     r9d, r9d; int
0x18000570f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005714  mov     ebx, eax
0x180005716  test    eax, eax
0x180005718  js      short loc_18000572C
0x18000571a  mov     rcx, rdi; this
0x18000571d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180005722  jmp     loc_180005648
0x180005727  mov     ebx, 80020009h
0x18000572c  mov     rcx, rbp; pv
0x18000572f  call    cs:__imp_CoTaskMemFree
0x180005735  mov     eax, ebx
0x180005737  mov     rcx, [rsp+2088h+var_48]
0x18000573f  xor     rcx, rsp; StackCookie
0x180005742  call    __security_check_cookie
0x180005747  add     rsp, 2050h
0x18000574e  pop     r15
0x180005750  pop     r14
0x180005752  pop     r13
0x180005754  pop     rdi
0x180005755  pop     rsi
0x180005756  pop     rbp
0x180005757  pop     rbx
0x180005758  retn
```
