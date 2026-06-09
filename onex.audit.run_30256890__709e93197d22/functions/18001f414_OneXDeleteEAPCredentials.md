# OneXDeleteEAPCredentials

- ea: `0x18001f414`
- end: `0x18001f47f`
- name: `OneXDeleteEAPCredentials`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019f7c`

## callees

- `0x18001f414`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x18001f45c`
- `MobileNetworking!FreeMemory` at `0x18001f45c`

## string_xrefs

- `0x18001f452`: `OneXDeleteEAPCredentials`

## pseudocode

```c
void __fastcall OneXDeleteEAPCredentials(__int64 a1)
{
  _QWORD *v2; // rdi
  _BYTE *v3; // rax
  __int64 v4; // rcx

  if ( a1 )
  {
    if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      if ( *(_DWORD *)(a1 + 44) )
      {
        v2 = (_QWORD *)(a1 + 48);
        v3 = *(_BYTE **)(a1 + 48);
        if ( v3 )
        {
          v4 = *(unsigned int *)(a1 + 44);
          do
          {
            *v3++ = 0;
            --v4;
          }
          while ( v4 );
          FreeMemory(v2, "OneXDeleteEAPCredentials", 286);
          *(_DWORD *)a1 &= ~4u;
          *(_QWORD *)(a1 + 40) = 0;
          *v2 = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001f414  test    rcx, rcx
0x18001f417  jz      short locret_18001F47E
0x18001f419  mov     [rsp+arg_0], rbx
0x18001f41e  push    rdi
0x18001f41f  sub     rsp, 20h
0x18001f423  test    byte ptr [rcx], 4
0x18001f426  mov     rbx, rcx
0x18001f429  jz      short loc_18001F474
0x18001f42b  cmp     dword ptr [rcx+2Ch], 0
0x18001f42f  jz      short loc_18001F474
0x18001f431  lea     rdi, [rcx+30h]
0x18001f435  mov     rax, [rdi]
0x18001f438  test    rax, rax
0x18001f43b  jz      short loc_18001F474
0x18001f43d  mov     ecx, [rcx+2Ch]
0x18001f440  mov     byte ptr [rax], 0
0x18001f443  inc     rax
0x18001f446  sub     rcx, 1
0x18001f44a  jnz     short loc_18001F440
0x18001f44c  mov     r8d, 11Eh
0x18001f452  lea     rdx, aOnexdeleteeapc; "OneXDeleteEAPCredentials"
0x18001f459  mov     rcx, rdi
0x18001f45c  call    cs:__imp_FreeMemory
0x18001f462  and     dword ptr [rbx], 0FFFFFFFBh
0x18001f465  mov     qword ptr [rbx+28h], 0
0x18001f46d  mov     qword ptr [rdi], 0
0x18001f474  mov     rbx, [rsp+28h+arg_0]
0x18001f479  add     rsp, 20h
0x18001f47d  pop     rdi
0x18001f47e  retn
```
