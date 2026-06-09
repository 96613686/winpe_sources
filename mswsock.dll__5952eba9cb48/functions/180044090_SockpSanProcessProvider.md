# SockpSanProcessProvider

- ea: `0x180044090`
- end: `0x1800442df`
- name: `SockpSanProcessProvider`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180038104`
- `0x18003847c`
- `0x1800384d4`
- `0x180038570`
- `0x18003aec4`
- `0x180043534`
- `0x180044090`
- `0x180044380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180044216`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180044216`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044233`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180044233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180044267`

## string_xrefs

- `0x180044208`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 __fastcall SockpSanProcessProvider(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4, __int64 a5, int a6)
{
  int i; // edx
  char *v9; // rbx
  __int64 v10; // rax
  int j; // ecx
  __int64 v12; // r10
  __int64 v13; // rdx
  PVOID *k; // rcx
  __int64 result; // rax
  HANDLE v16; // rax
  DWORD LastError; // eax
  __int64 v18; // rcx

  if ( a4 >= 0x10 )
  {
    for ( i = 0; i < SockProtocolInfoCount; ++i )
    {
      v9 = (char *)SockProtocolInfoArray + 628 * i;
      v10 = *(_QWORD *)(v9 + 20) - *a3;
      if ( !v10 )
        v10 = *(_QWORD *)(v9 + 28) - a3[1];
      if ( !v10 )
      {
        if ( v9 )
        {
          for ( j = 0; ; ++j )
          {
            if ( j >= a6 )
            {
              for ( k = (PVOID *)SockSanProviderList; k != &SockSanProviderList; k = (PVOID *)*k )
              {
                if ( *((_DWORD *)k + 10) == *((_DWORD *)v9 + 9) )
                {
                  if ( (xmmword_180063D60 & 2) != 0 )
                    WPP_SF_SS(
                      (_DWORD)k,
                      62,
                      (unsigned int)WPP_098f04338e83369a94575ae92ed301d7_Traceguids,
                      a1,
                      (__int64)(v9 + 116));
                  return 0;
                }
              }
              if ( *((_DWORD *)v9 + 19) != 23 || dword_180063524 )
              {
                if ( !SockSanHelperHandle )
                {
                  result = SockpSanRegister(k, a5, a3, a1);
                  if ( (int)result < 0 )
                    return result;
                }
                if ( (unsigned int)SockpSanLoadProvider((__int64)v9) == -1073741502 && !SockSanSCAutostartEvent )
                {
                  if ( (xmmword_180063D60 & 2) != 0 )
                    WPP_SF_(1025, 63, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
                  v16 = OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
                  SockSanSCAutostartEvent = v16;
                  if ( v16 )
                  {
                    if ( WaitForSingleObject(v16, 0) )
                    {
                      SockSanEnabled = 2;
                    }
                    else
                    {
                      if ( (xmmword_180063D60 & 2) != 0 )
                        WPP_SF_(1025, 64, WPP_098f04338e83369a94575ae92ed301d7_Traceguids);
                      CloseHandle(SockSanSCAutostartEvent);
                      SockSanSCAutostartEvent = (HANDLE)-1LL;
                    }
                  }
                  else if ( (xmmword_180063D60 & 2) != 0 )
                  {
                    LastError = GetLastError();
                    WPP_SF_l(v18, 65, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, LastError);
                  }
                }
              }
              return 0;
            }
            a3 = (_QWORD *)j;
            v12 = *(_QWORD *)(a5 + 8LL * j);
            if ( v12 )
            {
              if ( *(_DWORD *)(v12 + 40) == *((_DWORD *)v9 + 9) )
                break;
            }
          }
          *(_QWORD *)(a5 + 8LL * j) = 0;
          if ( (xmmword_180063D60 & 2) == 0 )
            return 0;
          v13 = 61;
          goto LABEL_42;
        }
        break;
      }
    }
    if ( (xmmword_180063D60 & 2) == 0 )
      return 0;
    v13 = 60;
LABEL_42:
    WPP_SF_S(1025, v13, WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1);
  }
  else if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_Sd(a1, 59, (unsigned int)WPP_098f04338e83369a94575ae92ed301d7_Traceguids, a1, a4);
  }
  return 0;
}

```

## disassembly

```asm
0x180044090  push    rbx
0x180044092  sub     rsp, 30h
0x180044096  mov     eax, r9d
0x180044099  mov     r9, rcx
0x18004409c  cmp     eax, 10h
0x18004409f  jnb     short loc_1800440C8
0x1800440a1  test    byte ptr cs:xmmword_180063D60, 2
0x1800440a8  jz      loc_1800442D6
0x1800440ae  mov     edx, 3Bh ; ';'
0x1800440b3  mov     dword ptr [rsp+38h+var_18], eax
0x1800440b7  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800440be  call    WPP_SF_Sd
0x1800440c3  jmp     loc_1800442D6
0x1800440c8  mov     r10, cs:SockProtocolInfoArray
0x1800440cf  xor     edx, edx
0x1800440d1  cmp     edx, cs:SockProtocolInfoCount
0x1800440d7  jge     loc_1800442B7
0x1800440dd  movsxd  rax, edx
0x1800440e0  imul    rbx, rax, 274h
0x1800440e7  add     rbx, r10
0x1800440ea  mov     rax, [rbx+14h]
0x1800440ee  sub     rax, [r8]
0x1800440f1  jnz     short loc_1800440FB
0x1800440f3  mov     rax, [rbx+1Ch]
0x1800440f7  sub     rax, [r8+8]
0x1800440fb  test    rax, rax
0x1800440fe  jz      short loc_180044104
0x180044100  inc     edx
0x180044102  jmp     short loc_1800440D1
0x180044104  test    rbx, rbx
0x180044107  jz      loc_1800442B7
0x18004410d  mov     rdx, [rsp+38h+arg_20]
0x180044112  xor     ecx, ecx
0x180044114  cmp     ecx, [rsp+38h+arg_28]
0x180044118  jge     short loc_180044152
0x18004411a  movsxd  r8, ecx
0x18004411d  mov     r10, [rdx+r8*8]
0x180044121  test    r10, r10
0x180044124  jz      short loc_18004412F
0x180044126  mov     eax, [rbx+24h]
0x180044129  cmp     [r10+28h], eax
0x18004412d  jz      short loc_180044133
0x18004412f  inc     ecx
0x180044131  jmp     short loc_180044114
0x180044133  mov     qword ptr [rdx+r8*8], 0
0x18004413b  test    byte ptr cs:xmmword_180063D60, 2
0x180044142  jz      loc_1800442D6
0x180044148  mov     edx, 3Dh ; '='
0x18004414d  jmp     loc_1800442C5
0x180044152  mov     rcx, cs:SockSanProviderList
0x180044159  lea     rax, SockSanProviderList
0x180044160  cmp     rcx, rax
0x180044163  jz      short loc_18004419E
0x180044165  mov     eax, [rbx+24h]
0x180044168  cmp     [rcx+28h], eax
0x18004416b  jz      short loc_180044172
0x18004416d  mov     rcx, [rcx]
0x180044170  jmp     short loc_180044159
0x180044172  test    byte ptr cs:xmmword_180063D60, 2
0x180044179  jz      loc_1800442D6
0x18004417f  lea     rax, [rbx+74h]
0x180044183  mov     edx, 3Eh ; '>'
0x180044188  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18004418f  mov     [rsp+38h+var_18], rax
0x180044194  call    WPP_SF_SS
0x180044199  jmp     loc_1800442D6
0x18004419e  cmp     dword ptr [rbx+4Ch], 17h
0x1800441a2  jnz     short loc_1800441B1
0x1800441a4  cmp     cs:dword_180063524, 0
0x1800441ab  jz      loc_1800442D6
0x1800441b1  cmp     cs:SockSanHelperHandle, 0
0x1800441b9  jnz     short loc_1800441C8
0x1800441bb  call    SockpSanRegister
0x1800441c0  test    eax, eax
0x1800441c2  js      loc_1800442D8
0x1800441c8  mov     rcx, rbx
0x1800441cb  call    SockpSanLoadProvider
0x1800441d0  cmp     eax, 0C0000142h
0x1800441d5  jnz     loc_1800442D6
0x1800441db  cmp     cs:SockSanSCAutostartEvent, 0
0x1800441e3  jnz     loc_1800442D6
0x1800441e9  test    byte ptr cs:xmmword_180063D60, 2
0x1800441f0  jz      short loc_180044208
0x1800441f2  mov     edx, 3Fh ; '?'
0x1800441f7  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800441fe  mov     ecx, 401h
0x180044203  call    WPP_SF_
0x180044208  lea     r8, Name; "Global\\SC_AutoStartComplete"
0x18004420f  xor     edx, edx; bInheritHandle
0x180044211  mov     ecx, 100000h; dwDesiredAccess
0x180044216  call    cs:__imp_OpenEventW
0x18004421d  nop     dword ptr [rax+rax+00h]
0x180044222  mov     cs:SockSanSCAutostartEvent, rax
0x180044229  test    rax, rax
0x18004422c  jz      short loc_18004428C
0x18004422e  xor     edx, edx; dwMilliseconds
0x180044230  mov     rcx, rax; hHandle
0x180044233  call    cs:__imp_WaitForSingleObject
0x18004423a  nop     dword ptr [rax+rax+00h]
0x18004423f  test    eax, eax
0x180044241  jnz     short loc_180044280
0x180044243  test    byte ptr cs:xmmword_180063D60, 2
0x18004424a  jz      short loc_180044260
0x18004424c  lea     edx, [rax+40h]
0x18004424f  mov     ecx, 401h
0x180044254  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x18004425b  call    WPP_SF_
0x180044260  mov     rcx, cs:SockSanSCAutostartEvent; hObject
0x180044267  call    cs:__imp_CloseHandle
0x18004426e  nop     dword ptr [rax+rax+00h]
0x180044273  mov     cs:SockSanSCAutostartEvent, 0FFFFFFFFFFFFFFFFh
0x18004427e  jmp     short loc_1800442D6
0x180044280  mov     cs:SockSanEnabled, 2
0x18004428a  jmp     short loc_1800442D6
0x18004428c  test    byte ptr cs:xmmword_180063D60, 2
0x180044293  jz      short loc_1800442D6
0x180044295  call    cs:__imp_GetLastError
0x18004429c  nop     dword ptr [rax+rax+00h]
0x1800442a1  mov     edx, 41h ; 'A'
0x1800442a6  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800442ad  mov     r9d, eax
0x1800442b0  call    WPP_SF_l
0x1800442b5  jmp     short loc_1800442D6
0x1800442b7  test    byte ptr cs:xmmword_180063D60, 2
0x1800442be  jz      short loc_1800442D6
0x1800442c0  mov     edx, 3Ch ; '<'
0x1800442c5  lea     r8, WPP_098f04338e83369a94575ae92ed301d7_Traceguids
0x1800442cc  mov     ecx, 401h
0x1800442d1  call    WPP_SF_S
0x1800442d6  xor     eax, eax
0x1800442d8  add     rsp, 30h
0x1800442dc  pop     rbx
0x1800442dd  retn
```
