# CheckFolders(void *,CFHEADER const &,CFRESERVE const &,CFFOLDER * *)

- ea: `0x18000d724`
- end: `0x18000d815`
- name: `?CheckFolders@@YAHPEAXAEBUCFHEADER@@AEBUCFRESERVE@@PEAPEAUCFFOLDER@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(void *, const struct CFHEADER *, const struct CFRESERVE *, struct CFFOLDER **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f5cc`

## callees

- `0x180002620`
- `0x18000d724`
- `0x18000e61c`
- `0x18000f4b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d75e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d75e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d7a1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d7a1`

## pseudocode

```c
__int64 __fastcall CheckFolders(void *a1, const struct CFHEADER *a2, const struct CFRESERVE *a3, struct CFFOLDER **a4)
{
  struct CFFOLDER *v8; // rax
  unsigned __int64 v9; // rdi
  unsigned int v10; // ebx
  _DWORD *v11; // r14
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  DWORD NumberOfBytesRead; // [rsp+34h] [rbp-44h] BYREF

  NumberOfBytesRead = 0;
  v8 = (struct CFFOLDER *)malloc(8LL * *((unsigned __int16 *)a2 + 13));
  *a4 = v8;
  if ( !v8 )
    return 0;
  v9 = 0;
  v10 = 1;
  while ( v9 < *((unsigned __int16 *)a2 + 13) )
  {
    v11 = (_DWORD *)((char *)*a4 + 8 * v9);
    if ( !ReadFile(a1, v11, 8u, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != 8
      || *v11 >= *((_DWORD *)a2 + 2)
      || *((_BYTE *)a3 + 2) && !SetFilePointerRelative(a1, *((unsigned __int8 *)a3 + 2)) )
    {
      return 0;
    }
    ++v9;
  }
  v13 = 0;
  if ( !(unsigned int)GetFilePointer(a1, &v13) || v13 != *((_DWORD *)a2 + 4) )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x18000d724  push    rbx
0x18000d726  push    rbp
0x18000d727  push    rsi
0x18000d728  push    rdi
0x18000d729  push    r12
0x18000d72b  push    r14
0x18000d72d  push    r15
0x18000d72f  sub     rsp, 40h
0x18000d733  mov     rax, cs:__security_cookie
0x18000d73a  xor     rax, rsp
0x18000d73d  mov     [rsp+78h+var_40], rax
0x18000d742  mov     rbp, rcx
0x18000d745  mov     [rsp+78h+NumberOfBytesRead], 0
0x18000d74d  movzx   ecx, word ptr [rdx+1Ah]
0x18000d751  mov     r12, r9
0x18000d754  shl     rcx, 3; Size
0x18000d758  mov     r15, r8
0x18000d75b  mov     rsi, rdx
0x18000d75e  call    cs:__imp_malloc
0x18000d764  mov     [r12], rax
0x18000d768  test    rax, rax
0x18000d76b  jz      loc_18000D7F5
0x18000d771  xor     edi, edi
0x18000d773  lea     ebx, [rdi+1]
0x18000d776  movzx   eax, word ptr [rsi+1Ah]
0x18000d77a  mov     rcx, rbp; void *
0x18000d77d  cmp     rdi, rax
0x18000d780  jnb     short loc_18000D7D6
0x18000d782  mov     rax, [r12]
0x18000d786  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d78b  mov     r8d, 8; nNumberOfBytesToRead
0x18000d791  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18000d79a  lea     r14, [rax+rdi*8]
0x18000d79e  mov     rdx, r14; lpBuffer
0x18000d7a1  call    cs:__imp_ReadFile
0x18000d7a7  test    eax, eax
0x18000d7a9  jz      short loc_18000D7F5
0x18000d7ab  cmp     [rsp+78h+NumberOfBytesRead], 8
0x18000d7b0  jnz     short loc_18000D7F5
0x18000d7b2  mov     eax, [rsi+8]
0x18000d7b5  cmp     [r14], eax
0x18000d7b8  jnb     short loc_18000D7F5
0x18000d7ba  movzx   eax, byte ptr [r15+2]
0x18000d7bf  test    al, al
0x18000d7c1  jz      short loc_18000D7D1
0x18000d7c3  mov     edx, eax; int
0x18000d7c5  mov     rcx, rbp; void *
0x18000d7c8  call    ?SetFilePointerRelative@@YAHPEAXJ@Z; SetFilePointerRelative(void *,long)
0x18000d7cd  test    eax, eax
0x18000d7cf  jz      short loc_18000D7F5
0x18000d7d1  add     rdi, rbx
0x18000d7d4  jmp     short loc_18000D776
0x18000d7d6  lea     rdx, [rsp+78h+var_48]; unsigned int *
0x18000d7db  mov     [rsp+78h+var_48], 0
0x18000d7e3  call    ?GetFilePointer@@YAHPEAXPEAK@Z; GetFilePointer(void *,ulong *)
0x18000d7e8  test    eax, eax
0x18000d7ea  jz      short loc_18000D7F5
0x18000d7ec  mov     eax, [rsi+10h]
0x18000d7ef  cmp     [rsp+78h+var_48], eax
0x18000d7f3  jz      short loc_18000D7F7
0x18000d7f5  xor     ebx, ebx
0x18000d7f7  mov     eax, ebx
0x18000d7f9  mov     rcx, [rsp+78h+var_40]
0x18000d7fe  xor     rcx, rsp; StackCookie
0x18000d801  call    __security_check_cookie
0x18000d806  add     rsp, 40h
0x18000d80a  pop     r15
0x18000d80c  pop     r14
0x18000d80e  pop     r12
0x18000d810  pop     rdi
0x18000d811  pop     rsi
0x18000d812  pop     rbp
0x18000d813  pop     rbx
0x18000d814  retn
```
