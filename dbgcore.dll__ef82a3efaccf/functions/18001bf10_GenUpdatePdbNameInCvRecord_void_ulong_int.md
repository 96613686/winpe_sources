# GenUpdatePdbNameInCvRecord(void *,ulong,int)

- ea: `0x18001bf10`
- end: `0x18001bfa6`
- name: `?GenUpdatePdbNameInCvRecord@@YAHPEAXKH@Z`
- size: `150`
- prototype: `__int64 __fastcall(char *, unsigned int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180017a38`
- `0x180017b8c`
- `0x18001a3f0`

## callees

- `0x1800021f4`
- `0x18001bf10`

## pseudocode

```c
__int64 __fastcall GenUpdatePdbNameInCvRecord(char *a1, unsigned int a2, int a3)
{
  unsigned int v3; // ebx
  __int64 v4; // r11
  char *v6; // rcx
  unsigned int v7; // r10d
  char *v8; // rdx
  char *v9; // r9
  char *v10; // r9
  char *v11; // rdx
  size_t v12; // r8

  v3 = 0;
  v4 = a2;
  if ( *(_DWORD *)a1 == 1396986706 )
  {
    v6 = a1 + 24;
    v7 = 24;
    v8 = 0;
    v9 = v6;
    if ( *v6 )
    {
      do
      {
        if ( v7 > (unsigned int)v4 )
          break;
        if ( *v9 == 92 )
          v8 = v9;
        ++v9;
        ++v7;
      }
      while ( *v9 );
      if ( v8 )
      {
        if ( v8 >= v6 )
        {
          v10 = &a1[v4];
          v11 = v8 + 1;
          if ( v11 < &a1[v4] )
          {
            v3 = 1;
            if ( a3 )
            {
              while ( *v11 && v11 < v10 )
                *v6++ = *v11++;
              v12 = v10 - v6;
              if ( v6 > v10 )
                v12 = 0;
              if ( v12 )
                memset_0(v6, 0, v12);
            }
          }
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001bf10  push    rbx
0x18001bf12  sub     rsp, 20h
0x18001bf16  xor     ebx, ebx
0x18001bf18  mov     r11d, edx
0x18001bf1b  cmp     dword ptr [rcx], 53445352h
0x18001bf21  mov     rax, rcx
0x18001bf24  jnz     short loc_18001BF9E
0x18001bf26  add     rcx, 18h
0x18001bf2a  lea     r10d, [rbx+18h]
0x18001bf2e  xor     edx, edx
0x18001bf30  mov     r9, rcx
0x18001bf33  cmp     [rcx], dl
0x18001bf35  jz      short loc_18001BF9E
0x18001bf37  cmp     r10d, r11d
0x18001bf3a  ja      short loc_18001BF4F
0x18001bf3c  cmp     byte ptr [r9], 5Ch ; '\'
0x18001bf40  cmovz   rdx, r9
0x18001bf44  inc     r9
0x18001bf47  inc     r10d
0x18001bf4a  cmp     [r9], bl
0x18001bf4d  jnz     short loc_18001BF37
0x18001bf4f  test    rdx, rdx
0x18001bf52  jz      short loc_18001BF9E
0x18001bf54  cmp     rdx, rcx
0x18001bf57  jb      short loc_18001BF9E
0x18001bf59  lea     r9, [rax+r11]
0x18001bf5d  inc     rdx
0x18001bf60  cmp     rdx, r9
0x18001bf63  jnb     short loc_18001BF9E
0x18001bf65  mov     ebx, 1
0x18001bf6a  test    r8d, r8d
0x18001bf6d  jz      short loc_18001BF9E
0x18001bf6f  jmp     short loc_18001BF80
0x18001bf71  cmp     rdx, r9
0x18001bf74  jnb     short loc_18001BF85
0x18001bf76  mov     al, [rdx]
0x18001bf78  mov     [rcx], al
0x18001bf7a  inc     rcx; void *
0x18001bf7d  inc     rdx
0x18001bf80  cmp     byte ptr [rdx], 0
0x18001bf83  jnz     short loc_18001BF71
0x18001bf85  xor     edx, edx; Val
0x18001bf87  mov     r8, r9
0x18001bf8a  sub     r8, rcx
0x18001bf8d  cmp     rcx, r9
0x18001bf90  cmova   r8, rdx; Size
0x18001bf94  test    r8, r8
0x18001bf97  jz      short loc_18001BF9E
0x18001bf99  call    memset_0
0x18001bf9e  mov     eax, ebx
0x18001bfa0  add     rsp, 20h
0x18001bfa4  pop     rbx
0x18001bfa5  retn
```
