# LcpConfigAckReceived

- ea: `0x180007020`
- end: `0x180007139`
- name: `LcpConfigAckReceived`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x180006328`
- `0x180007020`
- `0x180008338`
- `0x180033a74`

## pseudocode

```c
__int64 __fastcall LcpConfigAckReceived(_DWORD *a1, unsigned __int8 *a2)
{
  int v2; // esi
  int v3; // ebp
  __int64 v5; // r9
  __int64 result; // rax
  unsigned __int8 *v8; // rdx
  size_t v9; // r8
  __int64 v10; // rax
  __int64 v11; // r9
  char i; // cl
  int v13; // eax
  int v14[4]; // [rsp+20h] [rbp-628h] BYREF
  _BYTE Buf1[1504]; // [rsp+30h] [rbp-618h] BYREF

  v2 = a2[2];
  v3 = a2[3];
  v5 = (unsigned int)a1[302];
  v14[0] = 1500;
  result = BuildOptionList(Buf1, v14, a1 + 302, v5);
  if ( !(_DWORD)result )
  {
    v8 = a2 + 4;
    v9 = (unsigned int)((v2 << 8) + v3 - 4);
    if ( (_DWORD)v9 == v14[0] )
    {
      return memcmp_0(Buf1, v8, v9) != 0 ? 0x2D2 : 0;
    }
    else
    {
      if ( a1[2] && a1[305] == 49703 )
      {
        while ( (unsigned int)v9 >= 2 )
        {
          v10 = v8[1];
          if ( !(_BYTE)v10 )
            return 722;
          LODWORD(v9) = v9 - v10;
          if ( (v9 & 0x80000000) != 0LL )
            return 722;
          v11 = *v8;
          if ( (unsigned int)v10 < *((_DWORD *)qword_180037A80 + v11) || (_BYTE)v11 == 3 )
            return 722;
          v8 += v10;
        }
        a1[276] = 1;
        for ( i = 1; ; ++i )
        {
          v13 = 1 << i;
          if ( ((1 << i) & 0x10) != 0 )
            break;
          if ( (v13 & a1[275]) != 0 )
          {
            a1[276] = v13;
            break;
          }
        }
        MakeAuthProtocolOption((__int64)(a1 + 274));
      }
      return 722;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007020  push    rbx
0x180007022  push    rbp
0x180007023  push    rsi
0x180007024  push    rdi
0x180007025  sub     rsp, 628h
0x18000702c  mov     rax, cs:__security_cookie
0x180007033  xor     rax, rsp
0x180007036  mov     [rsp+648h+var_38], rax
0x18000703e  movzx   esi, byte ptr [rdx+2]
0x180007042  lea     r8, [rcx+4B8h]
0x180007049  movzx   ebp, byte ptr [rdx+3]
0x18000704d  mov     rdi, rdx
0x180007050  mov     r9d, [r8]
0x180007053  lea     rdx, [rsp+648h+var_628]
0x180007058  mov     rbx, rcx
0x18000705b  mov     [rsp+648h+var_628], 5DCh
0x180007063  lea     rcx, [rsp+648h+Buf1]
0x180007068  call    BuildOptionList
0x18000706d  test    eax, eax
0x18000706f  jnz     loc_18000711C
0x180007075  mov     ecx, esi
0x180007077  lea     rdx, [rdi+4]; Buf2
0x18000707b  shl     ecx, 8
0x18000707e  mov     r8d, ebp
0x180007081  add     r8d, 0FFFFFFFCh
0x180007085  add     r8d, ecx; Size
0x180007088  cmp     r8d, [rsp+648h+var_628]
0x18000708d  jz      short loc_180007109
0x18000708f  cmp     [rbx+8], eax
0x180007092  jz      short loc_180007102
0x180007094  cmp     dword ptr [rbx+4C4h], 0C227h
0x18000709e  jnz     short loc_180007102
0x1800070a0  cmp     r8d, 2
0x1800070a4  jb      short loc_1800070CF
0x1800070a6  movzx   eax, byte ptr [rdx+1]
0x1800070aa  test    al, al
0x1800070ac  jz      short loc_180007102
0x1800070ae  sub     r8d, eax
0x1800070b1  js      short loc_180007102
0x1800070b3  movzx   r9d, byte ptr [rdx]
0x1800070b7  lea     r10, qword_180037A80
0x1800070be  cmp     eax, [r10+r9*4]
0x1800070c2  jb      short loc_180007102
0x1800070c4  cmp     r9b, 3
0x1800070c8  jz      short loc_180007102
0x1800070ca  add     rdx, rax
0x1800070cd  jmp     short loc_1800070A0
0x1800070cf  mov     edx, 1
0x1800070d4  mov     [rbx+450h], edx
0x1800070da  mov     ecx, edx
0x1800070dc  mov     eax, edx
0x1800070de  shl     eax, cl
0x1800070e0  test    al, 10h
0x1800070e2  jnz     short loc_1800070F6
0x1800070e4  test    [rbx+44Ch], eax
0x1800070ea  jnz     short loc_1800070F0
0x1800070ec  add     ecx, edx
0x1800070ee  jmp     short loc_1800070DC
0x1800070f0  mov     [rbx+450h], eax
0x1800070f6  lea     rcx, [rbx+448h]
0x1800070fd  call    MakeAuthProtocolOption
0x180007102  mov     eax, 2D2h
0x180007107  jmp     short loc_18000711C
0x180007109  lea     rcx, [rsp+648h+Buf1]; Buf1
0x18000710e  call    memcmp_0
0x180007113  neg     eax
0x180007115  sbb     eax, eax
0x180007117  and     eax, 2D2h
0x18000711c  mov     rcx, [rsp+648h+var_38]
0x180007124  xor     rcx, rsp; StackCookie
0x180007127  call    __security_check_cookie
0x18000712c  add     rsp, 628h
0x180007133  pop     rdi
0x180007134  pop     rsi
0x180007135  pop     rbp
0x180007136  pop     rbx
0x180007137  retn
```
