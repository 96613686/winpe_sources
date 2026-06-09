# sha1_update

- ea: `0x1400910ec`
- end: `0x140091170`
- name: `sha1_update`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14009087c`

## callees

- `0x140090f04`
- `0x1400910ec`

## pseudocode

```c
__int64 __fastcall sha1_update(_DWORD *a1, char *a2, __int64 a3)
{
  __int64 v3; // rdi
  char *v4; // rsi
  unsigned int v6; // edx
  unsigned int v7; // ecx
  char v8; // al

  v3 = a3;
  v4 = a2;
  if ( a1 )
  {
    if ( !a3 )
      return 0;
    if ( a2 )
    {
      v6 = a1[23];
      do
      {
        v7 = a1[6];
        --v3;
        a1[6] = v7 + 8;
        if ( v7 >= v7 + 8 )
          ++a1[5];
        v8 = *v4++;
        *((_BYTE *)a1 + v6 + 28) = v8;
        v6 = a1[23] + 1;
        a1[23] = v6;
        if ( v6 == 64 )
        {
          sha1_process(a1);
          v6 = 0;
          a1[23] = 0;
        }
      }
      while ( v3 );
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1400910ec  mov     [rsp+arg_0], rbx
0x1400910f1  mov     [rsp+arg_8], rsi
0x1400910f6  push    rdi
0x1400910f7  sub     rsp, 20h
0x1400910fb  mov     rdi, r8
0x1400910fe  mov     rsi, rdx
0x140091101  mov     rbx, rcx
0x140091104  test    rcx, rcx
0x140091107  jz      short loc_14009115B
0x140091109  test    r8, r8
0x14009110c  jz      short loc_140091157
0x14009110e  test    rdx, rdx
0x140091111  jz      short loc_14009115B
0x140091113  mov     edx, [rcx+5Ch]
0x140091116  mov     ecx, [rbx+18h]
0x140091119  dec     rdi
0x14009111c  lea     eax, [rcx+8]
0x14009111f  mov     [rbx+18h], eax
0x140091122  cmp     ecx, eax
0x140091124  jbe     short loc_140091129
0x140091126  inc     dword ptr [rbx+14h]
0x140091129  mov     al, [rsi]
0x14009112b  inc     rsi
0x14009112e  mov     ecx, edx
0x140091130  mov     [rcx+rbx+1Ch], al
0x140091134  mov     edx, [rbx+5Ch]
0x140091137  inc     edx
0x140091139  mov     [rbx+5Ch], edx
0x14009113c  cmp     edx, 40h ; '@'
0x14009113f  jnz     short loc_140091152
0x140091141  mov     rcx, rbx
0x140091144  call    sha1_process
0x140091149  xor     edx, edx
0x14009114b  mov     dword ptr [rbx+5Ch], 0
0x140091152  test    rdi, rdi
0x140091155  jnz     short loc_140091116
0x140091157  xor     eax, eax
0x140091159  jmp     short loc_140091160
0x14009115b  mov     eax, 1
0x140091160  mov     rbx, [rsp+28h+arg_0]
0x140091165  mov     rsi, [rsp+28h+arg_8]
0x14009116a  add     rsp, 20h
0x14009116e  pop     rdi
0x14009116f  retn
```
