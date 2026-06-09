# getFileChecksum

- ea: `0x1400066f4`
- end: `0x14000682b`
- name: `getFileChecksum`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000488c`

## callees

- `0x1400066f4`
- `0x140008620`

## import_xrefs

- `msvcrt!_eof` at `0x1400067d8`
- `msvcrt!_eof` at `0x1400067d8`
- `msvcrt!_open` at `0x140006764`
- `msvcrt!_open` at `0x140006764`
- `msvcrt!_close` at `0x1400067ed`
- `msvcrt!_close` at `0x1400067ed`
- `msvcrt!_read` at `0x14000679f`
- `msvcrt!_read` at `0x14000679f`
- `msvcrt!malloc` at `0x14000671e`
- `msvcrt!malloc` at `0x14000671e`
- `msvcrt!free` at `0x1400067f6`
- `msvcrt!free` at `0x1400067f6`

## string_xrefs

- `0x140006782`: `Could not open file: %1`
- `0x14000681d`: `Read failure doing CRC on file: %1`

## pseudocode

```c
__int64 __fastcall getFileChecksum(__int64 a1, int *a2, __int64 a3)
{
  unsigned __int8 *v5; // rsi
  unsigned int v7; // r14d
  int v8; // edi
  int v9; // ebx
  int v10; // eax
  int v11; // edx
  unsigned __int8 *v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // rax
  int v15; // [rsp+60h] [rbp+8h] BYREF
  int v16; // [rsp+64h] [rbp+Ch]

  v16 = HIDWORD(a1);
  v15 = 0;
  *a2 = 0;
  v5 = (unsigned __int8 *)malloc(0x1000u);
  if ( v5 )
  {
    v7 = 0;
    v8 = _open(pszDest, 0x8000, &v15);
    if ( v8 == -1 )
    {
      ErrSet(a3, "Could not open file: %1", "%s", pszDest);
    }
    else
    {
      v9 = 0;
      while ( 1 )
      {
        if ( _eof(v8) )
        {
          v7 = 1;
          *a2 = v9;
          goto LABEL_13;
        }
        v10 = _read(v8, v5, 0x1000u);
        v11 = v10;
        if ( v10 == -1 )
          break;
        if ( v10 )
        {
          v12 = v5;
          v13 = ~v9;
          do
          {
            v14 = *v12++;
            v13 = *((_DWORD *)qword_1400110E0 + (v14 ^ (unsigned __int8)v13)) ^ (v13 >> 8);
            --v11;
          }
          while ( v11 );
          v9 = ~v13;
        }
      }
      ErrSet(a3, "Read failure doing CRC on file: %1", "%s", pszDest);
LABEL_13:
      _close(v8);
    }
    free(v5);
    return v7;
  }
  else
  {
    ErrSet(a3, "Out of memory doing CRC on file: %1", "%s", pszDest);
    return 0;
  }
}

```

## disassembly

```asm
0x1400066f4  mov     [rsp+arg_0], rcx
0x1400066f9  push    rbx
0x1400066fa  push    rbp
0x1400066fb  push    rsi
0x1400066fc  push    rdi
0x1400066fd  push    r14
0x1400066ff  push    r15
0x140006701  sub     rsp, 28h
0x140006705  mov     ecx, 1000h; Size
0x14000670a  mov     dword ptr [rsp+58h+arg_0], 0
0x140006712  mov     rbp, r8
0x140006715  mov     dword ptr [rdx], 0
0x14000671b  mov     r15, rdx
0x14000671e  call    cs:__imp_malloc
0x140006724  mov     rsi, rax
0x140006727  test    rax, rax
0x14000672a  jnz     short loc_140006750
0x14000672c  lea     r9, pszDest
0x140006733  mov     rcx, rbp
0x140006736  lea     r8, aS_4; "%s"
0x14000673d  lea     rdx, aOutOfMemoryDoi; "Out of memory doing CRC on file: %1"
0x140006744  call    ErrSet
0x140006749  xor     eax, eax
0x14000674b  jmp     loc_1400067FF
0x140006750  lea     r8, [rsp+58h+arg_0]
0x140006755  mov     edx, 8000h; OpenFlag
0x14000675a  lea     rcx, pszDest; FileName
0x140006761  xor     r14d, r14d
0x140006764  call    cs:__imp__open
0x14000676a  mov     edi, eax
0x14000676c  cmp     eax, 0FFFFFFFFh
0x14000676f  jnz     short loc_140006790
0x140006771  lea     r9, pszDest
0x140006778  mov     rcx, rbp
0x14000677b  lea     r8, aS_4; "%s"
0x140006782  lea     rdx, aCouldNotOpenFi; "Could not open file: %1"
0x140006789  call    ErrSet
0x14000678e  jmp     short loc_1400067F3
0x140006790  xor     ebx, ebx
0x140006792  jmp     short loc_1400067D6
0x140006794  mov     r8d, 1000h; MaxCharCount
0x14000679a  mov     rdx, rsi; DstBuf
0x14000679d  mov     ecx, edi; FileHandle
0x14000679f  call    cs:__imp__read
0x1400067a5  mov     edx, eax
0x1400067a7  cmp     eax, 0FFFFFFFFh
0x1400067aa  jz      short loc_14000680C
0x1400067ac  test    eax, eax
0x1400067ae  jz      short loc_1400067D6
0x1400067b0  mov     r8, rsi
0x1400067b3  not     ebx
0x1400067b5  movzx   eax, byte ptr [r8]
0x1400067b9  inc     r8
0x1400067bc  movzx   ecx, bl
0x1400067bf  xor     rcx, rax
0x1400067c2  shr     ebx, 8
0x1400067c5  lea     rax, qword_1400110E0
0x1400067cc  xor     ebx, [rax+rcx*4]
0x1400067cf  add     edx, 0FFFFFFFFh
0x1400067d2  jnz     short loc_1400067B5
0x1400067d4  not     ebx
0x1400067d6  mov     ecx, edi; FileHandle
0x1400067d8  call    cs:__imp__eof
0x1400067de  test    eax, eax
0x1400067e0  jz      short loc_140006794
0x1400067e2  mov     r14d, 1
0x1400067e8  mov     [r15], ebx
0x1400067eb  mov     ecx, edi; FileHandle
0x1400067ed  call    cs:__imp__close
0x1400067f3  mov     rcx, rsi; Block
0x1400067f6  call    cs:__imp_free
0x1400067fc  mov     eax, r14d
0x1400067ff  add     rsp, 28h
0x140006803  pop     r15
0x140006805  pop     r14
0x140006807  pop     rdi
0x140006808  pop     rsi
0x140006809  pop     rbp
0x14000680a  pop     rbx
0x14000680b  retn
0x14000680c  lea     r9, pszDest
0x140006813  mov     rcx, rbp
0x140006816  lea     r8, aS_4; "%s"
0x14000681d  lea     rdx, aReadFailureDoi; "Read failure doing CRC on file: %1"
0x140006824  call    ErrSet
0x140006829  jmp     short loc_1400067EB
```
