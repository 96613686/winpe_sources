# LipsDeleteQMIpsecFiltersForPolicy

- ea: `0x18004606c`
- end: `0x180046152`
- name: `LipsDeleteQMIpsecFiltersForPolicy`
- size: `230`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180044f5c`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004606c`
- `0x180047f60`
- `0x18004d090`

## string_xrefs

- `0x18004611f`: `LipsDeleteQMIpsecFiltersForPolicy`

## pseudocode

```c
__int64 __fastcall LipsDeleteQMIpsecFiltersForPolicy(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  __int64 v7; // rax
  GUID key; // [rsp+20h] [rbp-28h] BYREF

  key = 0;
  v4 = 0;
  while ( a1 )
  {
    v5 = *(_QWORD *)(a1 + 200);
    v6 = *(_QWORD **)(v5 + 8);
    v7 = *v6 - *a2;
    if ( *v6 == *a2 )
      v7 = v6[1] - a2[1];
    if ( !v7 )
    {
      if ( *(_QWORD *)(v5 + 16) )
      {
        key = *(GUID *)*(_QWORD *)v5;
        v4 = LipsBfeFilterDelete(&key);
        if ( v4 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, v4);
          }
          return LipsReportError(v4, "LipsDeleteQMIpsecFiltersForPolicy");
        }
      }
    }
    a1 = *(_QWORD *)(a1 + 208);
  }
  if ( v4 )
    return LipsReportError(v4, "LipsDeleteQMIpsecFiltersForPolicy");
  return 0;
}

```

## disassembly

```asm
0x18004606c  mov     [rsp+arg_8], rbx
0x180046071  mov     [rsp+arg_10], rsi
0x180046076  push    rdi
0x180046077  sub     rsp, 40h
0x18004607b  mov     rax, cs:__security_cookie
0x180046082  xor     rax, rsp
0x180046085  mov     [rsp+48h+var_18], rax
0x18004608a  xorps   xmm0, xmm0
0x18004608d  mov     rsi, rdx
0x180046090  movups  xmmword ptr [rsp+48h+key.Data1], xmm0
0x180046095  mov     rdi, rcx
0x180046098  xor     ebx, ebx
0x18004609a  test    rdi, rdi
0x18004609d  jz      loc_18004614A
0x1800460a3  mov     rcx, [rdi+0C8h]
0x1800460aa  mov     rdx, [rcx+8]
0x1800460ae  mov     rax, [rdx]
0x1800460b1  sub     rax, [rsi]
0x1800460b4  jnz     short loc_1800460BE
0x1800460b6  mov     rax, [rdx+8]
0x1800460ba  sub     rax, [rsi+8]
0x1800460be  test    rax, rax
0x1800460c1  jnz     short loc_1800460E5
0x1800460c3  cmp     [rcx+10h], rax
0x1800460c7  jz      short loc_1800460E5
0x1800460c9  mov     rax, [rcx]
0x1800460cc  lea     rcx, [rsp+48h+key]; key
0x1800460d1  movups  xmm0, xmmword ptr [rax]
0x1800460d4  movdqu  xmmword ptr [rsp+48h+key.Data1], xmm0
0x1800460da  call    LipsBfeFilterDelete
0x1800460df  mov     ebx, eax
0x1800460e1  test    eax, eax
0x1800460e3  jnz     short loc_1800460EE
0x1800460e5  mov     rdi, [rdi+0D0h]
0x1800460ec  jmp     short loc_18004609A
0x1800460ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800460f5  lea     rax, WPP_GLOBAL_Control
0x1800460fc  cmp     rcx, rax
0x1800460ff  jz      short loc_18004611F
0x180046101  test    byte ptr [rcx+1Ch], 10h
0x180046105  jz      short loc_18004611F
0x180046107  mov     rcx, [rcx+10h]
0x18004610b  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x180046112  mov     edx, 32h ; '2'
0x180046117  mov     r9d, ebx
0x18004611a  call    WPP_SF_d
0x18004611f  lea     rdx, aLipsdeleteqmip; "LipsDeleteQMIpsecFiltersForPolicy"
0x180046126  mov     ecx, ebx
0x180046128  call    LipsReportError
0x18004612d  mov     rcx, [rsp+48h+var_18]
0x180046132  xor     rcx, rsp; StackCookie
0x180046135  call    __security_check_cookie
0x18004613a  mov     rbx, [rsp+48h+arg_8]
0x18004613f  mov     rsi, [rsp+48h+arg_10]
0x180046144  add     rsp, 40h
0x180046148  pop     rdi
0x180046149  retn
0x18004614a  test    ebx, ebx
0x18004614c  jnz     short loc_18004611F
0x18004614e  xor     eax, eax
0x180046150  jmp     short loc_18004612D
```
