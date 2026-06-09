# CreateCompletionEntry

- ea: `0x18002f160`
- end: `0x18002f262`
- name: `CreateCompletionEntry`
- size: `258`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800409b4`

## callees

- `0x180006440`
- `0x18001c0d8`
- `0x18002f160`
- `0x18002f268`
- `0x18004d1a0`
- `0x18004dc0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f1f2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f1f2`

## pseudocode

```c
__int64 __fastcall CreateCompletionEntry(__int64 a1, _QWORD *a2)
{
  unsigned int LastErrorOrUnknown; // ebx
  _QWORD *v4; // rax
  HANDLE EventW; // rax
  _QWORD *v7; // [rsp+48h] [rbp+10h] BYREF

  v7 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dq(a1, 56, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, 1, a2);
  if ( a2 )
  {
    *a2 = 0;
    v4 = (_QWORD *)DhcpAlloc(40);
    v7 = v4;
    if ( v4 )
    {
      v4[1] = v4;
      *v4 = v4;
      v7[3] = 1;
      *((_DWORD *)v7 + 8) = 1;
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        LastErrorOrUnknown = 0;
        v7[2] = EventW;
        *a2 = v7;
        v7 = 0;
      }
      else
      {
        LastErrorOrUnknown = GetLastErrorOrUnknown();
      }
    }
    else
    {
      LastErrorOrUnknown = 8;
    }
  }
  else
  {
    LastErrorOrUnknown = 87;
  }
  if ( v7 )
    DestroyCompletionEntry(&v7);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 57, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, LastErrorOrUnknown);
  return LastErrorOrUnknown;
}

```

## disassembly

```asm
0x18002f160  mov     [rsp+arg_0], rbx
0x18002f165  push    rdi
0x18002f166  sub     rsp, 30h
0x18002f16a  mov     rdi, rdx
0x18002f16d  mov     [rsp+38h+arg_8], 0
0x18002f176  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002f17d  mov     ebx, 1
0x18002f182  jz      short loc_18002F19B
0x18002f184  lea     edx, [rbx+37h]
0x18002f187  mov     [rsp+38h+var_18], rdi
0x18002f18c  mov     r9d, ebx
0x18002f18f  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002f196  call    WPP_SF_dq
0x18002f19b  test    rdi, rdi
0x18002f19e  jnz     short loc_18002F1A5
0x18002f1a0  lea     ebx, [rdi+57h]
0x18002f1a3  jmp     short loc_18002F221
0x18002f1a5  mov     ecx, 28h ; '('
0x18002f1aa  mov     qword ptr [rdi], 0
0x18002f1b1  call    DhcpAlloc
0x18002f1b6  mov     [rsp+38h+arg_8], rax
0x18002f1bb  test    rax, rax
0x18002f1be  jnz     short loc_18002F1C5
0x18002f1c0  lea     ebx, [rax+8]
0x18002f1c3  jmp     short loc_18002F221
0x18002f1c5  mov     [rax+8], rax
0x18002f1c9  xor     r9d, r9d; lpName
0x18002f1cc  mov     [rax], rax
0x18002f1cf  xor     r8d, r8d; bInitialState
0x18002f1d2  mov     rax, [rsp+38h+arg_8]
0x18002f1d7  mov     edx, ebx; bManualReset
0x18002f1d9  xor     ecx, ecx; lpEventAttributes
0x18002f1db  mov     [rax+18h], ebx
0x18002f1de  mov     rax, [rsp+38h+arg_8]
0x18002f1e3  mov     dword ptr [rax+1Ch], 0
0x18002f1ea  mov     rax, [rsp+38h+arg_8]
0x18002f1ef  mov     [rax+20h], ebx
0x18002f1f2  call    cs:__imp_CreateEventW
0x18002f1f8  mov     rcx, rax
0x18002f1fb  test    rax, rax
0x18002f1fe  jnz     short loc_18002F209
0x18002f200  call    GetLastErrorOrUnknown
0x18002f205  mov     ebx, eax
0x18002f207  jmp     short loc_18002F221
0x18002f209  mov     rax, [rsp+38h+arg_8]
0x18002f20e  xor     ebx, ebx
0x18002f210  mov     [rax+10h], rcx
0x18002f214  mov     rax, [rsp+38h+arg_8]
0x18002f219  mov     [rdi], rax
0x18002f21c  mov     [rsp+38h+arg_8], rbx
0x18002f221  cmp     [rsp+38h+arg_8], 0
0x18002f227  jz      short loc_18002F233
0x18002f229  lea     rcx, [rsp+38h+arg_8]
0x18002f22e  call    DestroyCompletionEntry
0x18002f233  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002f23a  jz      short loc_18002F255
0x18002f23c  mov     edx, 39h ; '9'
0x18002f241  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18002f248  mov     ecx, 404h
0x18002f24d  mov     r9d, ebx
0x18002f250  call    WPP_SF_D
0x18002f255  mov     eax, ebx
0x18002f257  mov     rbx, [rsp+38h+arg_0]
0x18002f25c  add     rsp, 30h
0x18002f260  pop     rdi
0x18002f261  retn
```
