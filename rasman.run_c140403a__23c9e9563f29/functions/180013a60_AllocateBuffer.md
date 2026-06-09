# AllocateBuffer

- ea: `0x180013a60`
- end: `0x180013bdf`
- name: `AllocateBuffer`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f80`
- `0x180011b40`

## callees

- `0x180013a60`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013ab3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b87`

## pseudocode

```c
__int64 __fastcall AllocateBuffer(unsigned int a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v5; // ebx
  DWORD LastError; // ebp
  _DWORD *v7; // rax
  _QWORD *v9; // rcx
  USHORT v10; // dx

  *a2 = 0;
  if ( ~a1 < 0x1C00 )
  {
    LastError = 632;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v10 = 10;
LABEL_12:
    WPP_SF_d(v9[2], v10, &WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids, LastError);
    return LastError;
  }
  if ( a1 + 32 < a1 )
  {
    LastError = 534;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v10 = 11;
    goto LABEL_12;
  }
  v5 = a1 + 7168;
  if ( a1 + 7168 < a1 + 32 )
  {
    LastError = 534;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return LastError;
    }
    v10 = 12;
    goto LABEL_12;
  }
  LastError = 0;
  if ( v5 > *a3 )
  {
    v7 = LocalAlloc(0x40u, v5);
    *a2 = v7;
    if ( v7 )
    {
      v7[2] = 8;
      *a3 = v5;
      return LastError;
    }
    LastError = GetLastError();
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 13;
        goto LABEL_12;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180013a60  mov     [rsp+arg_8], rbp
0x180013a65  mov     [rsp+arg_10], rsi
0x180013a6a  push    rdi
0x180013a6b  sub     rsp, 20h
0x180013a6f  mov     eax, ecx
0x180013a71  mov     qword ptr [rdx], 0
0x180013a78  not     eax
0x180013a7a  mov     rsi, r8
0x180013a7d  mov     rdi, rdx
0x180013a80  cmp     eax, 1C00h
0x180013a85  jb      short loc_180013AE5
0x180013a87  lea     eax, [rcx+20h]
0x180013a8a  cmp     eax, ecx
0x180013a8c  jb      loc_180013B2A
0x180013a92  mov     [rsp+28h+arg_0], rbx
0x180013a97  lea     ebx, [rax+1BE0h]
0x180013a9d  cmp     ebx, eax
0x180013a9f  jb      loc_180013B50
0x180013aa5  xor     ebp, ebp
0x180013aa7  cmp     ebx, [r8]
0x180013aaa  jbe     short loc_180013ACE
0x180013aac  mov     edx, ebx; uBytes
0x180013aae  mov     ecx, 40h ; '@'; uFlags
0x180013ab3  call    cs:__imp_LocalAlloc
0x180013ab9  mov     [rdi], rax
0x180013abc  test    rax, rax
0x180013abf  jz      loc_180013B87
0x180013ac5  mov     dword ptr [rax+8], 8
0x180013acc  mov     [rsi], ebx
0x180013ace  mov     rbx, [rsp+28h+arg_0]
0x180013ad3  mov     rsi, [rsp+28h+arg_10]
0x180013ad8  mov     eax, ebp
0x180013ada  mov     rbp, [rsp+28h+arg_8]
0x180013adf  add     rsp, 20h
0x180013ae3  pop     rdi
0x180013ae4  retn
0x180013ae5  mov     ebp, 278h
0x180013aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180013af1  lea     rax, WPP_GLOBAL_Control
0x180013af8  cmp     rcx, rax
0x180013afb  jz      short loc_180013AD3
0x180013afd  test    byte ptr [rcx+1Ch], 40h
0x180013b01  jz      short loc_180013AD3
0x180013b03  cmp     byte ptr [rcx+19h], 2
0x180013b07  jb      short loc_180013AD3
0x180013b09  mov     edx, 0Ah
0x180013b0e  jmp     short loc_180013B15
0x180013b10  mov     edx, 0Bh
0x180013b15  mov     rcx, [rcx+10h]
0x180013b19  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180013b20  mov     r9d, ebp
0x180013b23  call    WPP_SF_d
0x180013b28  jmp     short loc_180013AD3
0x180013b2a  mov     ebp, 216h
0x180013b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b36  lea     rax, WPP_GLOBAL_Control
0x180013b3d  cmp     rcx, rax
0x180013b40  jz      short loc_180013AD3
0x180013b42  test    byte ptr [rcx+1Ch], 40h
0x180013b46  jz      short loc_180013AD3
0x180013b48  cmp     byte ptr [rcx+19h], 2
0x180013b4c  jb      short loc_180013AD3
0x180013b4e  jmp     short loc_180013B10
0x180013b50  mov     ebp, 216h
0x180013b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b5c  lea     rax, WPP_GLOBAL_Control
0x180013b63  cmp     rcx, rax
0x180013b66  jz      loc_180013ACE
0x180013b6c  test    byte ptr [rcx+1Ch], 40h
0x180013b70  jz      loc_180013ACE
0x180013b76  cmp     byte ptr [rcx+19h], 2
0x180013b7a  jb      loc_180013ACE
0x180013b80  mov     edx, 0Ch
0x180013b85  jmp     short loc_180013BC7
0x180013b87  call    cs:__imp_GetLastError
0x180013b8d  mov     ebp, eax
0x180013b8f  test    eax, eax
0x180013b91  jz      loc_180013ACE
0x180013b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b9e  lea     rax, WPP_GLOBAL_Control
0x180013ba5  cmp     rcx, rax
0x180013ba8  jz      loc_180013ACE
0x180013bae  test    byte ptr [rcx+1Ch], 40h
0x180013bb2  jz      loc_180013ACE
0x180013bb8  cmp     byte ptr [rcx+19h], 2
0x180013bbc  jb      loc_180013ACE
0x180013bc2  mov     edx, 0Dh
0x180013bc7  mov     rcx, [rcx+10h]
0x180013bcb  lea     r8, WPP_f28ad74b0d6a36eca7ee1ca540e33602_Traceguids
0x180013bd2  mov     r9d, ebp
0x180013bd5  call    WPP_SF_d
0x180013bda  jmp     loc_180013ACE
```
