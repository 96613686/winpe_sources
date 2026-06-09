# SpGetContextToken(unsigned __int64,void * *)

- ea: `0x180019600`
- end: `0x18001968c`
- name: `?SpGetContextToken@@YAJ_KPEAPEAX@Z`
- size: `140`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ebcc`
- `0x18000ec28`
- `0x180019124`
- `0x180019600`

## pseudocode

```c
__int64 __fastcall SpGetContextToken(unsigned __int64 a1, void **a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids);
  v4 = WSTGetContextToken(a1, a2);
  v5 = v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids, v4);
  return v5;
}

```

## disassembly

```asm
0x180019600  mov     [rsp+arg_0], rbx
0x180019605  mov     [rsp+arg_8], rsi
0x18001960a  push    rdi
0x18001960b  sub     rsp, 20h
0x18001960f  mov     rbx, rdx
0x180019612  mov     rdi, rcx
0x180019615  mov     rcx, cs:WPP_GLOBAL_Control
0x18001961c  lea     rsi, WPP_GLOBAL_Control
0x180019623  cmp     rcx, rsi
0x180019626  jz      short loc_180019643
0x180019628  test    byte ptr [rcx+1Ch], 8
0x18001962c  jz      short loc_180019643
0x18001962e  mov     rcx, [rcx+10h]
0x180019632  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x180019639  mov     edx, 20h ; ' '
0x18001963e  call    WPP_SF_
0x180019643  mov     rdx, rbx; void **
0x180019646  mov     rcx, rdi; unsigned __int64
0x180019649  call    ?WSTGetContextToken@@YAJ_KPEAPEAX@Z; WSTGetContextToken(unsigned __int64,void * *)
0x18001964e  mov     ebx, eax
0x180019650  mov     rcx, cs:WPP_GLOBAL_Control
0x180019657  cmp     rcx, rsi
0x18001965a  jz      short loc_18001967A
0x18001965c  test    byte ptr [rcx+1Ch], 8
0x180019660  jz      short loc_18001967A
0x180019662  mov     rcx, [rcx+10h]
0x180019666  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x18001966d  mov     edx, 21h ; '!'
0x180019672  mov     r9d, eax
0x180019675  call    WPP_SF_d
0x18001967a  mov     rsi, [rsp+28h+arg_8]
0x18001967f  mov     eax, ebx
0x180019681  mov     rbx, [rsp+28h+arg_0]
0x180019686  add     rsp, 20h
0x18001968a  pop     rdi
0x18001968b  retn
```
