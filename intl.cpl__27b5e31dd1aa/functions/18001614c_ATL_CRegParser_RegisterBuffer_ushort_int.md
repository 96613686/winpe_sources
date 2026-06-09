# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18001614c`
- end: `0x1800162b6`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800162bc`

## callees

- `0x180015890`
- `0x180015db4`
- `0x18001614c`
- `0x18001646c`
- `0x180016d04`
- `0x18002a150`
- `0x18002a210`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800161ea`
- `KERNEL32!lstrcmpiW` at `0x1800161d1`
- `KERNEL32!lstrcmpiW` at `0x1800161d1`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
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
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
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
      while ( **(_WORD **)this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x18001614c  push    rbx
0x18001614e  push    rbp
0x18001614f  push    rsi
0x180016150  push    rdi
0x180016151  push    r13
0x180016153  push    r14
0x180016155  push    r15
0x180016157  mov     eax, 2050h
0x18001615c  call    _alloca_probe
0x180016161  sub     rsp, rax
0x180016164  mov     rax, cs:__security_cookie
0x18001616b  xor     rax, rsp
0x18001616e  mov     [rsp+2088h+var_48], rax
0x180016176  mov     r15d, r8d
0x180016179  mov     [rsp+2088h+pv], 0
0x180016182  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180016187  mov     rdi, rcx
0x18001618a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18001618f  mov     ebx, eax
0x180016191  test    eax, eax
0x180016193  js      short loc_1800161F2
0x180016195  mov     rbp, [rsp+2088h+pv]
0x18001619a  xor     eax, eax
0x18001619c  mov     [rdi], rbp
0x18001619f  cmp     ax, [rbp+0]
0x1800161a3  jz      short loc_1800161E7
0x1800161a5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800161ac  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800161b1  mov     rcx, rdi; this
0x1800161b4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800161b9  mov     ebx, eax
0x1800161bb  test    eax, eax
0x1800161bd  js      short loc_1800161E7
0x1800161bf  xor     ebx, ebx
0x1800161c1  movsxd  rsi, ebx
0x1800161c4  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800161c9  add     rsi, rsi
0x1800161cc  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800161d1  call    cs:__imp_lstrcmpiW
0x1800161d7  test    eax, eax
0x1800161d9  jz      short loc_180016214
0x1800161db  inc     ebx
0x1800161dd  cmp     ebx, 0Eh
0x1800161e0  jb      short loc_1800161C1
0x1800161e2  mov     ebx, 80020009h
0x1800161e7  mov     rcx, rbp; pv
0x1800161ea  call    cs:__imp_CoTaskMemFree
0x1800161f0  mov     eax, ebx
0x1800161f2  mov     rcx, [rsp+2088h+var_48]
0x1800161fa  xor     rcx, rsp; StackCookie
0x1800161fd  call    __security_check_cookie
0x180016202  add     rsp, 2050h
0x180016209  pop     r15
0x18001620b  pop     r14
0x18001620d  pop     r13
0x18001620f  pop     rdi
0x180016210  pop     rsi
0x180016211  pop     rbp
0x180016212  pop     rbx
0x180016213  retn
0x180016214  mov     rsi, [r13+rsi*8+8]
0x180016219  test    rsi, rsi
0x18001621c  jz      short loc_1800161E2
0x18001621e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180016223  mov     rcx, rdi; this
0x180016226  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001622b  mov     ebx, eax
0x18001622d  test    eax, eax
0x18001622f  js      short loc_1800161E7
0x180016231  mov     eax, 7Bh ; '{'
0x180016236  cmp     ax, [rsp+2088h+String1]
0x18001623b  jnz     short loc_1800161E2
0x18001623d  mov     [rsp+2088h+var_2068], 0; int
0x180016245  mov     r8, rsi; HKEY
0x180016248  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001624d  mov     rcx, rdi; this
0x180016250  test    r15d, r15d
0x180016253  jz      short loc_180016289
0x180016255  mov     r14, [rdi]
0x180016258  mov     r9d, r15d; int
0x18001625b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180016260  mov     ebx, eax
0x180016262  test    eax, eax
0x180016264  jns     short loc_18001629B
0x180016266  xor     r9d, r9d; int
0x180016269  mov     [rdi], r14
0x18001626c  mov     r8, rsi; HKEY
0x18001626f  mov     [rsp+2088h+var_2068], 0; int
0x180016277  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001627c  mov     rcx, rdi; this
0x18001627f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180016284  jmp     loc_1800161E7
0x180016289  xor     r9d, r9d; int
0x18001628c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180016291  mov     ebx, eax
0x180016293  test    eax, eax
0x180016295  js      loc_1800161E7
0x18001629b  mov     rcx, rdi; this
0x18001629e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800162a3  mov     rcx, [rdi]
0x1800162a6  xor     eax, eax
0x1800162a8  cmp     ax, [rcx]
0x1800162ab  jnz     loc_1800161AC
0x1800162b1  jmp     loc_1800161E7
```
