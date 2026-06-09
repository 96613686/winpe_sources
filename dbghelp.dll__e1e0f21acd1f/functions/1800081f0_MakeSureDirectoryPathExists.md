# MakeSureDirectoryPathExists

- ea: `0x1800081f0`
- end: `0x1800083f0`
- name: `MakeSureDirectoryPathExists`
- size: `512`
- prototype: `BOOL __stdcall(PCSTR DirPath)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800081f0`
- `0x180008400`
- `0x1800084a0`
- `0x1800086a0`
- `0x1800086fc`
- `0x1800089f0`
- `0x180008ad0`
- `0x180008b38`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180008333`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x180008333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008344`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008344`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800083e5`

## pseudocode

```c
BOOL __stdcall MakeSureDirectoryPathExists(PCSTR DirPath)
{
  unsigned __int64 v2; // rbx
  _BYTE *v3; // rax
  _BYTE *v4; // rdi
  _BYTE *v5; // rbx
  unsigned int FileAttributes; // eax
  _BYTE *v8; // rcx
  char i; // al
  char v10; // dl
  _BYTE *v11; // rax
  char v12; // cl
  unsigned __int64 v13; // [rsp+38h] [rbp+10h] BYREF

  v13 = 0;
  if ( !(unsigned int)LengthOfUntrustedStringA(DirPath, &v13) || !v13 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v2 = v13 + 1;
  if ( v13 + 1 < v13 )
    return 0;
  v3 = (_BYTE *)pMemAlloc(v13 + 1);
  v4 = v3;
  if ( !v3 )
    return 0;
  if ( !(unsigned int)CopyUntrustedMemory(v3, DirPath, v2) )
  {
LABEL_18:
    FreeIt(v4);
    return 0;
  }
  if ( *v4 == 92 && v4[1] == 92 )
  {
    v8 = v4 + 2;
    for ( i = v4[2]; i && i != 92; i = *v8 )
      v8 = (_BYTE *)((__int64 (*)(void))CharNext)();
    if ( *v8 )
      v10 = v8[1];
    else
      v10 = 0;
    v11 = v8 + 1;
    if ( !*v8 )
      v11 = v8;
    if ( v10 )
    {
      v12 = *v11;
      do
      {
        if ( v12 == 92 )
          break;
        v11 = (_BYTE *)CharNext(v11);
        v12 = *v11;
      }
      while ( *v11 );
    }
    v5 = v11 + 1;
    if ( !*v11 )
      v5 = v11;
  }
  else if ( v4[1] == 58 )
  {
    v5 = v4 + 2;
    if ( v4[2] == 92 )
      v5 = v4 + 3;
  }
  else
  {
    v5 = v4;
  }
  while ( *v5 )
  {
    if ( *v5 == 92 )
    {
      *v5 = 0;
      FileAttributes = afnGetFileAttributes(v4);
      if ( FileAttributes == -1 )
      {
        if ( !CreateDirectoryA(v4, 0) && GetLastError() != 183 )
          goto LABEL_18;
      }
      else if ( (FileAttributes & 0x10) == 0 )
      {
        goto LABEL_18;
      }
      *v5 = 92;
    }
    LoadDynamicCalls(&g_CoreLocalizationCallsDesc);
    LoadDynamicCalls(&g_Kernel32CallsDesc);
    SetLastError(0x7Eu);
    if ( *v5 )
      ++v5;
  }
  FreeIt(v4);
  return 1;
}

```

## disassembly

```asm
0x1800081f0  mov     rax, rsp
0x1800081f3  mov     [rax+8], rbx
0x1800081f7  mov     [rax+18h], rsi
0x1800081fb  push    rdi
0x1800081fc  sub     rsp, 20h
0x180008200  lea     rdx, [rax+10h]; unsigned __int64 *
0x180008204  mov     qword ptr [rax+10h], 0
0x18000820c  mov     rsi, rcx
0x18000820f  call    ?LengthOfUntrustedStringA@@YAHPEBDPEA_K@Z; LengthOfUntrustedStringA(char const *,unsigned __int64 *)
0x180008214  test    eax, eax
0x180008216  jz      loc_18000833F
0x18000821c  mov     rax, [rsp+28h+arg_8]
0x180008221  test    rax, rax
0x180008224  jz      loc_18000833F
0x18000822a  lea     rbx, [rax+1]
0x18000822e  cmp     rbx, rax
0x180008231  jb      loc_180008305
0x180008237  mov     rcx, rbx; dwBytes
0x18000823a  call    pMemAlloc
0x18000823f  mov     rdi, rax
0x180008242  test    rax, rax
0x180008245  jz      loc_180008305
0x18000824b  mov     r8, rbx; unsigned __int64
0x18000824e  mov     rdx, rsi; void *
0x180008251  mov     rcx, rax; void *
0x180008254  call    ?CopyUntrustedMemory@@YAHPEAXPEBX_K@Z; CopyUntrustedMemory(void *,void const *,unsigned __int64)
0x180008259  test    eax, eax
0x18000825b  jz      loc_1800082FD
0x180008261  cmp     byte ptr [rdi], 5Ch ; '\'
0x180008264  jz      loc_18000834C
0x18000826a  cmp     byte ptr [rdi+1], 3Ah ; ':'
0x18000826e  jnz     loc_180008326
0x180008274  lea     rbx, [rdi+2]
0x180008278  cmp     byte ptr [rbx], 5Ch ; '\'
0x18000827b  jz      loc_1800083B0
0x180008281  mov     sil, [rbx]
0x180008284  test    sil, sil
0x180008287  jz      loc_180008317
0x18000828d  cmp     sil, 5Ch ; '\'
0x180008291  jz      short loc_1800082D4
0x180008293  lea     rcx, ?g_CoreLocalizationCallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_CoreLocalizationCallsDesc
0x18000829a  call    LoadDynamicCalls
0x18000829f  test    eax, eax
0x1800082a1  jnz     loc_1800083B8
0x1800082a7  mov     rax, cs:qword_1802EC1F0
0x1800082ae  test    rax, rax
0x1800082b1  jz      loc_1800083B8
0x1800082b7  mov     rax, cs:qword_1802EC1F0
0x1800082be  mov     cl, sil
0x1800082c1  call    rax ; qword_1802EC1F0
0x1800082c3  test    eax, eax
0x1800082c5  jz      short loc_1800082CA
0x1800082c7  inc     rbx
0x1800082ca  cmp     byte ptr [rbx], 0
0x1800082cd  jz      short loc_180008281
0x1800082cf  inc     rbx
0x1800082d2  jmp     short loc_180008281
0x1800082d4  mov     rcx, rdi; lpFileName
0x1800082d7  mov     byte ptr [rbx], 0
0x1800082da  call    ?afnGetFileAttributes@@YAKPEBD@Z; afnGetFileAttributes(char const *)
0x1800082df  cmp     eax, 0FFFFFFFFh
0x1800082e2  jz      short loc_18000832E
0x1800082e4  test    al, 10h
0x1800082e6  jz      short loc_1800082FD
0x1800082e8  mov     byte ptr [rbx], 5Ch ; '\'
0x1800082eb  mov     sil, 5Ch ; '\'
0x1800082ee  jmp     short loc_180008293
0x1800082f0  call    cs:__imp_GetLastError
0x1800082f6  cmp     eax, 0B7h
0x1800082fb  jz      short loc_1800082E8
0x1800082fd  mov     rcx, rdi; lpMem
0x180008300  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x180008305  xor     eax, eax
0x180008307  mov     rbx, [rsp+28h+arg_0]
0x18000830c  mov     rsi, [rsp+28h+arg_10]
0x180008311  add     rsp, 20h
0x180008315  pop     rdi
0x180008316  retn
0x180008317  mov     rcx, rdi; lpMem
0x18000831a  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x18000831f  mov     eax, 1
0x180008324  jmp     short loc_180008307
0x180008326  mov     rbx, rdi
0x180008329  jmp     loc_180008281
0x18000832e  xor     edx, edx; lpSecurityAttributes
0x180008330  mov     rcx, rdi; lpPathName
0x180008333  call    cs:__imp_CreateDirectoryA
0x180008339  test    eax, eax
0x18000833b  jz      short loc_1800082F0
0x18000833d  jmp     short loc_1800082E8
0x18000833f  mov     ecx, 57h ; 'W'; dwErrCode
0x180008344  call    cs:__imp_SetLastError
0x18000834a  jmp     short loc_180008305
0x18000834c  cmp     byte ptr [rdi+1], 5Ch ; '\'
0x180008350  jnz     loc_18000826A
0x180008356  lea     rcx, [rdi+2]
0x18000835a  mov     al, [rcx]
0x18000835c  jmp     short loc_18000836C
0x18000835e  cmp     al, 5Ch ; '\'
0x180008360  jz      short loc_180008370
0x180008362  call    CharNext
0x180008367  mov     rcx, rax
0x18000836a  mov     al, [rax]
0x18000836c  test    al, al
0x18000836e  jnz     short loc_18000835E
0x180008370  cmp     byte ptr [rcx], 0
0x180008373  jz      short loc_18000837A
0x180008375  mov     dl, [rcx+1]
0x180008378  jmp     short loc_18000837C
0x18000837a  xor     dl, dl
0x18000837c  cmp     byte ptr [rcx], 0
0x18000837f  lea     rax, [rcx+1]
0x180008383  cmovz   rax, rcx
0x180008387  test    dl, dl
0x180008389  jz      short loc_1800083A0
0x18000838b  mov     cl, [rax]
0x18000838d  cmp     cl, 5Ch ; '\'
0x180008390  jz      short loc_1800083A0
0x180008392  mov     rcx, rax
0x180008395  call    CharNext
0x18000839a  mov     cl, [rax]
0x18000839c  test    cl, cl
0x18000839e  jnz     short loc_18000838D
0x1800083a0  cmp     byte ptr [rax], 0
0x1800083a3  lea     rbx, [rax+1]
0x1800083a7  cmovz   rbx, rax
0x1800083ab  jmp     loc_180008281
0x1800083b0  inc     rbx
0x1800083b3  jmp     loc_180008281
0x1800083b8  lea     rcx, ?g_Kernel32CallsDesc@@3U_DYNAMIC_CALLS_DESC@@C; _DYNAMIC_CALLS_DESC volatile g_Kernel32CallsDesc
0x1800083bf  call    LoadDynamicCalls
0x1800083c4  test    eax, eax
0x1800083c6  jnz     short loc_1800083E0
0x1800083c8  mov     rax, cs:qword_1802EC7D0
0x1800083cf  test    rax, rax
0x1800083d2  jz      short loc_1800083E0
0x1800083d4  mov     rax, cs:qword_1802EC7D0
0x1800083db  jmp     loc_1800082BE
0x1800083e0  mov     ecx, 7Eh ; '~'; dwErrCode
0x1800083e5  call    cs:__imp_SetLastError
0x1800083eb  jmp     loc_1800082CA
```
