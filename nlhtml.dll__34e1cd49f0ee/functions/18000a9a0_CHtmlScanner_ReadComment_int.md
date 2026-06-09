# CHtmlScanner::ReadComment(int)

- ea: `0x18000a9a0`
- end: `0x18000aaaa`
- name: `?ReadComment@CHtmlScanner@@AEAAXH@Z`
- size: `266`
- prototype: `void __fastcall(CHtmlScanner *__hidden this, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007aa0`
- `0x180008210`
- `0x180008690`

## callees

- `0x180007094`
- `0x180009700`
- `0x18000a374`
- `0x18000a9a0`
- `0x1800104d0`

## pseudocode

```c
void __fastcall CHtmlScanner::ReadComment(CHtmlScanner *this, int a2)
{
  int v4; // ebx
  __int64 v5; // rax
  wchar_t Char; // ax
  wchar_t v7; // si

  *((_DWORD *)this + 7) = 0;
  v4 = 0;
  while ( 1 )
  {
    v5 = *((_QWORD *)this + 1);
    if ( *(__int16 *)(v5 + 40) <= 0
      && *(_QWORD *)(v5 + 88) >= v5 + 2 * ((unsigned __int64)*(unsigned int *)(v5 + 84) + 21)
      && !*(_DWORD *)(v5 + 116)
      && *(_DWORD *)(v5 + 100) >= *(_DWORD *)(v5 + 104)
      && *(_DWORD *)(v5 + 96) == *(_DWORD *)(v5 + 296)
      && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v5 + 288)) )
    {
      break;
    }
    Char = CSerialStream::GetChar(*((CSerialStream **)this + 1));
    v7 = Char;
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        v4 = 2;
        if ( Char != 45 )
          v4 = 0;
      }
      else
      {
        if ( Char == 62 )
        {
          if ( !a2 )
            return;
          *((_DWORD *)this + 7) -= 2;
          break;
        }
        if ( Char != 45 )
          v4 = 0;
      }
    }
    else
    {
      v4 = Char == 45;
    }
    if ( a2 )
    {
      if ( *((_DWORD *)this + 7) >= *((_DWORD *)this + 6) && (int)CHtmlScanner::GrowTagBuffer(this) < 0 )
        break;
      *(_WORD *)(*((_QWORD *)this + 2) + 2LL * (unsigned int)(*((_DWORD *)this + 7))++) = v7;
    }
  }
  FixPrivateChars_0(*((_QWORD *)this + 2), *((unsigned int *)this + 7));
}

```

## disassembly

```asm
0x18000a9a0  push    rbx
0x18000a9a2  push    rbp
0x18000a9a3  push    rdi
0x18000a9a4  push    r14
0x18000a9a6  sub     rsp, 28h
0x18000a9aa  mov     ebp, edx
0x18000a9ac  mov     dword ptr [rcx+1Ch], 0
0x18000a9b3  mov     rdi, rcx
0x18000a9b6  mov     [rsp+48h+arg_0], rsi
0x18000a9bb  xor     ebx, ebx
0x18000a9bd  mov     r14d, 1
0x18000a9c3  mov     rax, [rdi+8]
0x18000a9c7  cmp     word ptr [rax+28h], 0
0x18000a9cc  jg      short loc_18000A9DF
0x18000a9ce  mov     edx, [rax+54h]
0x18000a9d1  add     rdx, 15h
0x18000a9d5  lea     rdx, [rax+rdx*2]
0x18000a9d9  cmp     [rax+58h], rdx
0x18000a9dd  jnb     short loc_18000AA17
0x18000a9df  mov     rcx, [rdi+8]; this
0x18000a9e3  call    ?GetChar@CSerialStream@@QEAA_WXZ; CSerialStream::GetChar(void)
0x18000a9e8  movzx   esi, ax
0x18000a9eb  test    ebx, ebx
0x18000a9ed  jnz     short loc_18000AA3F
0x18000a9ef  cmp     ax, 2Dh ; '-'
0x18000a9f3  cmovz   ebx, r14d
0x18000a9f7  test    ebp, ebp
0x18000a9f9  jz      short loc_18000A9C3
0x18000a9fb  mov     eax, [rdi+18h]
0x18000a9fe  cmp     [rdi+1Ch], eax
0x18000aa01  jnb     loc_18000AA98
0x18000aa07  mov     ecx, [rdi+1Ch]
0x18000aa0a  mov     rax, [rdi+10h]
0x18000aa0e  mov     [rax+rcx*2], si
0x18000aa12  inc     dword ptr [rdi+1Ch]
0x18000aa15  jmp     short loc_18000A9C3
0x18000aa17  cmp     dword ptr [rax+74h], 0
0x18000aa1b  jnz     short loc_18000A9DF
0x18000aa1d  mov     ecx, [rax+68h]
0x18000aa20  cmp     [rax+64h], ecx
0x18000aa23  jb      short loc_18000A9DF
0x18000aa25  lea     rcx, [rax+120h]; this
0x18000aa2c  mov     edx, [rcx+8]
0x18000aa2f  cmp     [rax+60h], edx
0x18000aa32  jnz     short loc_18000A9DF
0x18000aa34  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x18000aa39  test    eax, eax
0x18000aa3b  jz      short loc_18000A9DF
0x18000aa3d  jmp     short loc_18000AA59
0x18000aa3f  mov     eax, ebx
0x18000aa41  sub     eax, r14d
0x18000aa44  jz      short loc_18000AA74
0x18000aa46  cmp     eax, r14d
0x18000aa49  jnz     short loc_18000A9F7
0x18000aa4b  cmp     si, 3Eh ; '>'
0x18000aa4f  jnz     short loc_18000AA87
0x18000aa51  test    ebp, ebp
0x18000aa53  jz      short loc_18000AA65
0x18000aa55  add     dword ptr [rdi+1Ch], 0FFFFFFFEh
0x18000aa59  mov     edx, [rdi+1Ch]
0x18000aa5c  mov     rcx, [rdi+10h]
0x18000aa60  call    FixPrivateChars_0
0x18000aa65  mov     rsi, [rsp+48h+arg_0]
0x18000aa6a  add     rsp, 28h
0x18000aa6e  pop     r14
0x18000aa70  pop     rdi
0x18000aa71  pop     rbp
0x18000aa72  pop     rbx
0x18000aa73  retn
0x18000aa74  xor     eax, eax
0x18000aa76  mov     ebx, 2
0x18000aa7b  cmp     si, 2Dh ; '-'
0x18000aa7f  cmovnz  ebx, eax
0x18000aa82  jmp     loc_18000A9F7
0x18000aa87  cmp     si, 2Dh ; '-'
0x18000aa8b  jz      loc_18000A9F7
0x18000aa91  xor     ebx, ebx
0x18000aa93  jmp     loc_18000A9F7
0x18000aa98  mov     rcx, rdi; this
0x18000aa9b  call    ?GrowTagBuffer@CHtmlScanner@@AEAAJXZ; CHtmlScanner::GrowTagBuffer(void)
0x18000aaa0  test    eax, eax
0x18000aaa2  jns     loc_18000AA07
0x18000aaa8  jmp     short loc_18000AA59
```
