# SkipUntilEndOfComment

- ea: `0x100287b0`
- end: `0x10028855`
- name: `SkipUntilEndOfComment`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10025cc0`
- `0x10028640`

## callees

- `0x100287b0`
- `0x100288d0`
- `0x10028a60`

## pseudocode

```c
int __stdcall SkipUntilEndOfComment(int a1)
{
  int *v1; // esi
  int v2; // edi
  int result; // eax
  LONG v4; // ebx
  unsigned int v5; // ebp

  v1 = (int *)a1;
  v2 = 1;
  while ( 1 )
  {
    result = TextReadHTMLFile(v1, v1[10], &a1, 1);
    if ( result < 0 )
      return result;
    if ( (_WORD)a1 == 45 )
    {
      v4 = v1[1];
      v5 = dword_10041B74;
      result = TextReadHTMLFile(v1, v1[10], &a1, 1);
      if ( result < 0 )
        return result;
      if ( (_WORD)a1 == 45 )
      {
        a1 = 32;
        while ( 1 )
        {
          result = TextReadHTMLFile(v1, v1[10], &a1, 1);
          if ( result < 0 )
            return result;
          if ( (_WORD)a1 != 32 )
          {
            if ( (_WORD)a1 != 62 )
              break;
            --v2;
            goto LABEL_12;
          }
        }
      }
      TextSetHTMLFilePosition(v1, v1[10], 0, v4, v5);
LABEL_12:
      if ( v2 <= 0 )
        return 0;
    }
  }
}

```

## disassembly

```asm
0x100287b0  push    ebx
0x100287b1  push    ebp
0x100287b2  push    esi
0x100287b3  mov     esi, [esp+0Ch+arg_0]
0x100287b7  push    edi
0x100287b8  mov     edi, 1
0x100287bd  lea     ecx, [ecx+0]
0x100287c0  push    1
0x100287c2  lea     eax, [esp+14h+arg_0]
0x100287c6  push    eax
0x100287c7  push    dword ptr [esi+28h]
0x100287ca  push    esi
0x100287cb  call    TextReadHTMLFile
0x100287d0  test    eax, eax
0x100287d2  js      short loc_1002884E
0x100287d4  cmp     word ptr [esp+10h+arg_0], 2Dh ; '-'
0x100287da  jnz     short loc_100287C0
0x100287dc  mov     ebx, [esi+4]
0x100287df  lea     eax, [esp+10h+arg_0]
0x100287e3  mov     ebp, dword_10041B74
0x100287e9  push    1
0x100287eb  push    eax
0x100287ec  push    dword ptr [esi+28h]
0x100287ef  push    esi
0x100287f0  call    TextReadHTMLFile
0x100287f5  test    eax, eax
0x100287f7  js      short loc_1002884E
0x100287f9  cmp     word ptr [esp+10h+arg_0], 2Dh ; '-'
0x100287ff  jnz     short loc_10028837
0x10028801  mov     [esp+10h+arg_0], 20h ; ' '
0x10028809  lea     esp, [esp+0]
0x10028810  push    1
0x10028812  lea     eax, [esp+14h+arg_0]
0x10028816  push    eax
0x10028817  push    dword ptr [esi+28h]
0x1002881a  push    esi
0x1002881b  call    TextReadHTMLFile
0x10028820  test    eax, eax
0x10028822  js      short loc_1002884E
0x10028824  mov     eax, [esp+10h+arg_0]
0x10028828  cmp     ax, 20h ; ' '
0x1002882c  jz      short loc_10028810
0x1002882e  cmp     ax, 3Eh ; '>'
0x10028832  jnz     short loc_10028837
0x10028834  dec     edi
0x10028835  jmp     short loc_10028844
0x10028837  push    ebp; int
0x10028838  push    ebx; lDistanceToMove
0x10028839  push    0; int
0x1002883b  push    dword ptr [esi+28h]; int
0x1002883e  push    esi; int
0x1002883f  call    TextSetHTMLFilePosition
0x10028844  test    edi, edi
0x10028846  jg      loc_100287C0
0x1002884c  xor     eax, eax
0x1002884e  pop     edi
0x1002884f  pop     esi
0x10028850  pop     ebp
0x10028851  pop     ebx
0x10028852  retn    4
```
