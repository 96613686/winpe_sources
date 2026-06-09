# BackupSourceTable::EqualValue(__BackSourceRecord &,__BackSourceRecord &,int,ulong)

- ea: `0x18006a1e0`
- end: `0x18006a2f4`
- name: `?EqualValue@BackupSourceTable@@UEAAHAEAU__BackSourceRecord@@0HK@Z`
- size: `276`
- prototype: `__int64 __fastcall(BackupSourceTable *__hidden this, struct __BackSourceRecord *, struct __BackSourceRecord *, int, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18006a1e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18006a246`
- `msvcrt!_wcsicmp` at `0x18006a276`
- `msvcrt!_wcsicmp` at `0x18006a246`
- `msvcrt!_wcsicmp` at `0x18006a276`
- `KERNEL32!CompareFileTime` at `0x18006a2a2`
- `KERNEL32!CompareFileTime` at `0x18006a2ce`
- `KERNEL32!CompareFileTime` at `0x18006a2a2`
- `KERNEL32!CompareFileTime` at `0x18006a2ce`

## pseudocode

```c
__int64 __fastcall BackupSourceTable::EqualValue(
        BackupSourceTable *this,
        struct __BackSourceRecord *a2,
        struct __BackSourceRecord *a3,
        int a4,
        char a5)
{
  unsigned int v5; // ecx
  struct __BackSourceRecord *v9; // rax
  __int64 v10; // rcx
  int v11; // edx
  int v12; // r8d

  v5 = 1;
  if ( (a5 & 1) == 0 )
    goto LABEL_17;
  v9 = a2;
  v10 = a3 - a2;
  do
  {
    v11 = *(unsigned __int16 *)((char *)v9 + v10);
    v12 = *(unsigned __int16 *)v9 - v11;
    if ( v12 )
      break;
    v9 = (struct __BackSourceRecord *)((char *)v9 + 2);
  }
  while ( v11 );
  v5 = v12 == 0;
  if ( v5 == a4 )
  {
LABEL_17:
    if ( (a5 & 2) == 0 || (v5 = _wcsicmp((const wchar_t *)a2 + 256, (const wchar_t *)a3 + 256) == 0, v5 == a4) )
    {
      if ( (a5 & 8) == 0 || (v5 = _wcsicmp((const wchar_t *)a2 + 518, (const wchar_t *)a3 + 518) == 0, v5 == a4) )
      {
        if ( (a5 & 0x10) == 0
          || (v5 = CompareFileTime((const FILETIME *)a2 + 195, (const FILETIME *)a3 + 195) == 0, v5 == a4) )
        {
          if ( (a5 & 0x20) != 0 )
            return CompareFileTime((const FILETIME *)a2 + 196, (const FILETIME *)a3 + 196) == 0;
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18006a1e0  mov     [rsp+arg_0], rbp
0x18006a1e5  mov     [rsp+arg_8], rsi
0x18006a1ea  push    rdi
0x18006a1eb  sub     rsp, 20h
0x18006a1ef  mov     ecx, 1
0x18006a1f4  mov     ebp, r9d
0x18006a1f7  mov     rdi, r8
0x18006a1fa  mov     rsi, rdx
0x18006a1fd  test    [rsp+28h+arg_20], cl
0x18006a201  jz      short loc_18006A231
0x18006a203  mov     rcx, r8
0x18006a206  mov     rax, rdx
0x18006a209  sub     rcx, rdx
0x18006a20c  movzx   r8d, word ptr [rax]
0x18006a210  movzx   edx, word ptr [rax+rcx]
0x18006a214  sub     r8d, edx
0x18006a217  jnz     short loc_18006A221
0x18006a219  add     rax, 2
0x18006a21d  test    edx, edx
0x18006a21f  jnz     short loc_18006A20C
0x18006a221  xor     ecx, ecx
0x18006a223  test    r8d, r8d
0x18006a226  setz    cl
0x18006a229  cmp     ecx, ebp
0x18006a22b  jnz     loc_18006A2E1
0x18006a231  test    [rsp+28h+arg_20], 2
0x18006a236  jz      short loc_18006A261
0x18006a238  lea     rdx, [rdi+200h]; String2
0x18006a23f  lea     rcx, [rsi+200h]; String1
0x18006a246  call    cs:__imp__wcsicmp
0x18006a24d  nop     dword ptr [rax+rax+00h]
0x18006a252  xor     ecx, ecx
0x18006a254  test    eax, eax
0x18006a256  setz    cl
0x18006a259  cmp     ecx, ebp
0x18006a25b  jnz     loc_18006A2E1
0x18006a261  test    [rsp+28h+arg_20], 8
0x18006a266  jz      short loc_18006A28D
0x18006a268  lea     rdx, [rdi+40Ch]; String2
0x18006a26f  lea     rcx, [rsi+40Ch]; String1
0x18006a276  call    cs:__imp__wcsicmp
0x18006a27d  nop     dword ptr [rax+rax+00h]
0x18006a282  xor     ecx, ecx
0x18006a284  test    eax, eax
0x18006a286  setz    cl
0x18006a289  cmp     ecx, ebp
0x18006a28b  jnz     short loc_18006A2E1
0x18006a28d  test    [rsp+28h+arg_20], 10h
0x18006a292  jz      short loc_18006A2B9
0x18006a294  lea     rdx, [rdi+618h]; lpFileTime2
0x18006a29b  lea     rcx, [rsi+618h]; lpFileTime1
0x18006a2a2  call    cs:__imp_CompareFileTime
0x18006a2a9  nop     dword ptr [rax+rax+00h]
0x18006a2ae  xor     ecx, ecx
0x18006a2b0  test    eax, eax
0x18006a2b2  setz    cl
0x18006a2b5  cmp     ecx, ebp
0x18006a2b7  jnz     short loc_18006A2E1
0x18006a2b9  test    [rsp+28h+arg_20], 20h
0x18006a2be  jz      short loc_18006A2E1
0x18006a2c0  lea     rdx, [rdi+620h]; lpFileTime2
0x18006a2c7  lea     rcx, [rsi+620h]; lpFileTime1
0x18006a2ce  call    cs:__imp_CompareFileTime
0x18006a2d5  nop     dword ptr [rax+rax+00h]
0x18006a2da  xor     ecx, ecx
0x18006a2dc  test    eax, eax
0x18006a2de  setz    cl
0x18006a2e1  mov     rbp, [rsp+28h+arg_0]
0x18006a2e6  mov     eax, ecx
0x18006a2e8  mov     rsi, [rsp+28h+arg_8]
0x18006a2ed  add     rsp, 20h
0x18006a2f1  pop     rdi
0x18006a2f2  retn
```
