# McGenControlCallbackV2

- ea: `0x14001f880`
- end: `0x14001f97f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001f880`
- `0x14001fd40`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          v10 = 0;
          if ( *(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
            if ( !v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v10 = 1;
            }
          }
          v11 = 1 << v7;
          v12 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x14001f880  push    rbx
0x14001f882  sub     rsp, 20h
0x14001f886  mov     r10, [rsp+28h+CallbackContext]
0x14001f88b  xor     ebx, ebx
0x14001f88d  test    r10, r10
0x14001f890  jz      loc_14001F978
0x14001f896  test    edx, edx
0x14001f898  jz      loc_14001F93F
0x14001f89e  cmp     edx, 1
0x14001f8a1  jnz     loc_14001F978
0x14001f8a7  mov     rax, [rsp+28h+MatchAllKeyword]
0x14001f8ac  mov     [r10+28h], r8b
0x14001f8b0  mov     r8d, ebx
0x14001f8b3  mov     [r10+18h], rax
0x14001f8b7  mov     [r10+10h], r9
0x14001f8bb  mov     [r10+24h], edx
0x14001f8bf  cmp     bx, [r10+2Ah]
0x14001f8c4  jnb     loc_14001F978
0x14001f8ca  mov     rax, [r10+40h]
0x14001f8ce  mov     cl, [r10+28h]
0x14001f8d2  mov     r9d, r8d
0x14001f8d5  cmp     [r9+rax], cl
0x14001f8d9  jbe     short loc_14001F8DF
0x14001f8db  test    cl, cl
0x14001f8dd  jnz     short loc_14001F901
0x14001f8df  mov     rax, [r10+38h]
0x14001f8e3  mov     rdx, [rax+r9*8]
0x14001f8e7  test    rdx, rdx
0x14001f8ea  jz      short loc_14001F906
0x14001f8ec  test    [r10+10h], rdx
0x14001f8f0  jz      short loc_14001F901
0x14001f8f2  mov     rcx, [r10+18h]
0x14001f8f6  mov     rax, rcx
0x14001f8f9  and     rax, rdx
0x14001f8fc  cmp     rax, rcx
0x14001f8ff  jz      short loc_14001F906
0x14001f901  mov     r11b, bl
0x14001f904  jmp     short loc_14001F909
0x14001f906  mov     r11b, 1
0x14001f909  mov     rax, [r10+30h]
0x14001f90d  mov     ecx, r8d
0x14001f910  shr     r9, 5
0x14001f914  mov     edx, 1
0x14001f919  shl     edx, cl
0x14001f91b  lea     rcx, [rax+r9*4]
0x14001f91f  mov     eax, [rcx]
0x14001f921  test    r11b, r11b
0x14001f924  jz      short loc_14001F92A
0x14001f926  or      edx, eax
0x14001f928  jmp     short loc_14001F92E
0x14001f92a  not     edx
0x14001f92c  and     edx, eax
0x14001f92e  mov     [rcx], edx
0x14001f930  inc     r8d
0x14001f933  movzx   eax, word ptr [r10+2Ah]
0x14001f938  cmp     r8d, eax
0x14001f93b  jb      short loc_14001F8CA
0x14001f93d  jmp     short loc_14001F978
0x14001f93f  movzx   eax, word ptr [r10+2Ah]
0x14001f944  mov     [r10+24h], ebx
0x14001f948  mov     [r10+28h], bl
0x14001f94c  mov     [r10+10h], rbx
0x14001f950  mov     [r10+18h], rbx
0x14001f954  test    ax, ax
0x14001f957  jz      short loc_14001F978
0x14001f959  mov     rcx, [r10+30h]; void *
0x14001f95d  dec     eax
0x14001f95f  cdq
0x14001f960  and     edx, 1Fh
0x14001f963  add     eax, edx
0x14001f965  xor     edx, edx; Val
0x14001f967  sar     eax, 5
0x14001f96a  inc     eax
0x14001f96c  movsxd  r8, eax
0x14001f96f  shl     r8, 2; Size
0x14001f973  call    memset
0x14001f978  add     rsp, 20h
0x14001f97c  pop     rbx
0x14001f97d  retn
```
