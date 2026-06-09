# GenSystemQueueFormatName(__MIDL___MIDL_itf_mqtrig_0000_0000_0002,_bstr_t *)

- ea: `0x1800174d4`
- end: `0x1800175d3`
- name: `?GenSystemQueueFormatName@@YAJW4__MIDL___MIDL_itf_mqtrig_0000_0000_0002@@PEAV_bstr_t@@@Z`
- size: `255`
- prototype: `DWORD __fastcall(int, _bstr_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010590`
- `0x180012f40`

## callees

- `0x180005740`
- `0x18000c654`
- `0x180012c84`
- `0x1800174d4`
- `0x18001e380`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x18001750a`
- `KERNEL32!GetComputerNameW` at `0x18001750a`
- `KERNEL32!GetLastError` at `0x180017514`
- `KERNEL32!GetLastError` at `0x180017514`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall GenSystemQueueFormatName(int a1, _bstr_t *a2)
{
  int v5; // ebx
  int v6; // ebx
  const wchar_t *v7; // rax
  int v8; // eax
  DWORD nSize; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Buffer[20]; // [rsp+38h] [rbp-440h] BYREF
  wchar_t v11[512]; // [rsp+60h] [rbp-418h] BYREF

  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
    return GetLastError();
  v5 = a1 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return 1;
      v7 = L";DEADXACT";
    }
    else
    {
      v7 = L";DEADLETTER";
    }
  }
  else
  {
    v7 = L";JOURNAL";
  }
  v8 = StringCchPrintfW(v11, 0x200u, L"DIRECT=OS:%s\\SYSTEM$%s", Buffer, v7);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids,
        (unsigned int)v8);
    return 1;
  }
  _bstr_t::operator=(a2, v11);
  return 0;
}

```

## disassembly

```asm
0x1800174d4  mov     [rsp+arg_0], rbx
0x1800174d9  push    rdi
0x1800174da  sub     rsp, 470h
0x1800174e1  mov     rax, cs:__security_cookie
0x1800174e8  xor     rax, rsp
0x1800174eb  mov     [rsp+478h+var_18], rax
0x1800174f3  mov     rdi, rdx
0x1800174f6  mov     [rsp+478h+nSize], 10h
0x1800174fe  mov     ebx, ecx
0x180017500  lea     rdx, [rsp+478h+nSize]; nSize
0x180017505  lea     rcx, [rsp+478h+Buffer]; lpBuffer
0x18001750a  call    cs:__imp_GetComputerNameW
0x180017510  test    eax, eax
0x180017512  jnz     short loc_18001751F
0x180017514  call    cs:__imp_GetLastError
0x18001751a  jmp     loc_1800175B2
0x18001751f  sub     ebx, 1
0x180017522  jz      short loc_180017540
0x180017524  sub     ebx, 1
0x180017527  jz      short loc_180017537
0x180017529  cmp     ebx, 1
0x18001752c  jnz     short loc_18001759C
0x18001752e  lea     rax, aDeadxact; ";DEADXACT"
0x180017535  jmp     short loc_180017547
0x180017537  lea     rax, aDeadletter; ";DEADLETTER"
0x18001753e  jmp     short loc_180017547
0x180017540  lea     rax, aJournal; ";JOURNAL"
0x180017547  lea     r9, [rsp+478h+Buffer]
0x18001754c  mov     [rsp+478h+var_458], rax
0x180017551  lea     r8, aDirectOsSSyste; "DIRECT=OS:%s\\SYSTEM$%s"
0x180017558  mov     edx, 200h; unsigned __int64
0x18001755d  lea     rcx, [rsp+478h+var_418]; wchar_t *
0x180017562  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180017567  test    eax, eax
0x180017569  jns     short loc_1800175A3
0x18001756b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017572  lea     r8, WPP_GLOBAL_Control
0x180017579  cmp     rcx, r8
0x18001757c  jz      short loc_18001759C
0x18001757e  test    byte ptr [rcx+1Ch], 1
0x180017582  jz      short loc_18001759C
0x180017584  mov     rcx, [rcx+10h]
0x180017588  lea     r8, WPP_f17d2b29d4b8365f8ea91b4848b968c5_Traceguids
0x18001758f  mov     edx, 10h
0x180017594  mov     r9d, eax
0x180017597  call    WPP_SF_d
0x18001759c  mov     eax, 1
0x1800175a1  jmp     short loc_1800175B2
0x1800175a3  lea     rdx, [rsp+478h+var_418]
0x1800175a8  mov     rcx, rdi
0x1800175ab  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x1800175b0  xor     eax, eax
0x1800175b2  mov     rcx, [rsp+478h+var_18]
0x1800175ba  xor     rcx, rsp; StackCookie
0x1800175bd  call    __security_check_cookie
0x1800175c2  mov     rbx, [rsp+478h+arg_0]
0x1800175ca  add     rsp, 470h
0x1800175d1  pop     rdi
0x1800175d2  retn
```
