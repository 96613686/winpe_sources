# LcpConfigAckReceived

- ea: `0x180006d70`
- end: `0x180006e88`
- name: `LcpConfigAckReceived`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001460`
- `0x1800060b4`
- `0x180006d70`
- `0x180008048`
- `0x180032454`

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
          if ( (unsigned int)v10 < *((_DWORD *)qword_180036A80 + v11) || (_BYTE)v11 == 3 )
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
        MakeAuthProtocolOption(a1 + 274);
      }
      return 722;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006d70  push    rbx
0x180006d72  push    rbp
0x180006d73  push    rsi
0x180006d74  push    rdi
0x180006d75  sub     rsp, 628h
0x180006d7c  mov     rax, cs:__security_cookie
0x180006d83  xor     rax, rsp
0x180006d86  mov     [rsp+648h+var_38], rax
0x180006d8e  movzx   esi, byte ptr [rdx+2]
0x180006d92  lea     r8, [rcx+4B8h]
0x180006d99  movzx   ebp, byte ptr [rdx+3]
0x180006d9d  mov     rdi, rdx
0x180006da0  mov     r9d, [r8]
0x180006da3  lea     rdx, [rsp+648h+var_628]
0x180006da8  mov     rbx, rcx
0x180006dab  mov     [rsp+648h+var_628], 5DCh
0x180006db3  lea     rcx, [rsp+648h+Buf1]
0x180006db8  call    BuildOptionList
0x180006dbd  test    eax, eax
0x180006dbf  jnz     loc_180006E6C
0x180006dc5  mov     ecx, esi
0x180006dc7  lea     rdx, [rdi+4]; Buf2
0x180006dcb  shl     ecx, 8
0x180006dce  mov     r8d, ebp
0x180006dd1  add     r8d, 0FFFFFFFCh
0x180006dd5  add     r8d, ecx; Size
0x180006dd8  cmp     r8d, [rsp+648h+var_628]
0x180006ddd  jz      short loc_180006E59
0x180006ddf  cmp     [rbx+8], eax
0x180006de2  jz      short loc_180006E52
0x180006de4  cmp     dword ptr [rbx+4C4h], 0C227h
0x180006dee  jnz     short loc_180006E52
0x180006df0  cmp     r8d, 2
0x180006df4  jb      short loc_180006E1F
0x180006df6  movzx   eax, byte ptr [rdx+1]
0x180006dfa  test    al, al
0x180006dfc  jz      short loc_180006E52
0x180006dfe  sub     r8d, eax
0x180006e01  js      short loc_180006E52
0x180006e03  movzx   r9d, byte ptr [rdx]
0x180006e07  lea     r10, qword_180036A80
0x180006e0e  cmp     eax, [r10+r9*4]
0x180006e12  jb      short loc_180006E52
0x180006e14  cmp     r9b, 3
0x180006e18  jz      short loc_180006E52
0x180006e1a  add     rdx, rax
0x180006e1d  jmp     short loc_180006DF0
0x180006e1f  mov     edx, 1
0x180006e24  mov     [rbx+450h], edx
0x180006e2a  mov     ecx, edx
0x180006e2c  mov     eax, edx
0x180006e2e  shl     eax, cl
0x180006e30  test    al, 10h
0x180006e32  jnz     short loc_180006E46
0x180006e34  test    [rbx+44Ch], eax
0x180006e3a  jnz     short loc_180006E40
0x180006e3c  add     ecx, edx
0x180006e3e  jmp     short loc_180006E2C
0x180006e40  mov     [rbx+450h], eax
0x180006e46  lea     rcx, [rbx+448h]
0x180006e4d  call    MakeAuthProtocolOption
0x180006e52  mov     eax, 2D2h
0x180006e57  jmp     short loc_180006E6C
0x180006e59  lea     rcx, [rsp+648h+Buf1]; Buf1
0x180006e5e  call    memcmp_0
0x180006e63  neg     eax
0x180006e65  sbb     eax, eax
0x180006e67  and     eax, 2D2h
0x180006e6c  mov     rcx, [rsp+648h+var_38]
0x180006e74  xor     rcx, rsp; StackCookie
0x180006e77  call    __security_check_cookie
0x180006e7c  add     rsp, 628h
0x180006e83  pop     rdi
0x180006e84  pop     rsi
0x180006e85  pop     rbp
0x180006e86  pop     rbx
0x180006e87  retn
```
