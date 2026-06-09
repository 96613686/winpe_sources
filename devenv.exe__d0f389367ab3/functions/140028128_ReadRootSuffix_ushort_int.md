# ReadRootSuffix(ushort *,int)

- ea: `0x140028128`
- end: `0x1400282a9`
- name: `?ReadRootSuffix@@YAXPEAGH@Z`
- size: `385`
- prototype: `void __fastcall(wchar_t *Buffer, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000ccfc`
- `0x140027e30`

## callees

- `0x140001020`
- `0x14002143c`
- `0x140028128`
- `0x140033090`
- `0x1400638f8`
- `0x140063d86`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x140028187`
- `KERNEL32!GetModuleFileNameW` at `0x140028187`
- `api-ms-win-crt-stdio-l1-1-0!fgetws` at `0x140028252`
- `api-ms-win-crt-stdio-l1-1-0!fgetws` at `0x140028252`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x14002823a`
- `api-ms-win-crt-stdio-l1-1-0!_wfopen_s` at `0x14002823a`

## pseudocode

```c
void __fastcall ReadRootSuffix(wchar_t *Buffer)
{
  unsigned __int64 ModuleFileNameW; // rax
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax
  wchar_t *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rbx
  FILE *Stream; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t Source[12]; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t Filename[280]; // [rsp+40h] [rbp-C0h] BYREF

  *Buffer = 0;
  wcscpy(Source, L".rootsuffix");
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( ModuleFileNameW >= 273 )
    _report_rangecheckfailure(v3);
  v4 = -1;
  Filename[ModuleFileNameW] = 0;
  v5 = -1;
  do
    ++v5;
  while ( Filename[v5] );
  v6 = &Source[v5 + 8];
  if ( wcsicmp_0(v6, L".exe") )
  {
    *Buffer = 0;
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( Filename[v7] );
    wcscpy_s_0(v6, 277 - v7, Source);
    Stream = 0;
    _wfopen_s(&Stream, Filename, L"r");
    if ( Stream )
    {
      if ( fgetws(Buffer, 260, Stream) )
      {
        do
          ++v4;
        while ( Buffer[v4] );
        if ( v4 && Buffer[v4 - 1] == 10 )
          Buffer[v4 - 1] = 0;
        v8 = v4 - 1;
        if ( v8 )
        {
          if ( Buffer[v8 - 1] == 32 )
            Buffer[v8 - 1] = 0;
        }
      }
      else
      {
        *Buffer = 0;
      }
      fclose_0(Stream);
    }
  }
}

```

## disassembly

```asm
0x140028128  mov     [rsp-8+arg_8], rbx
0x14002812d  mov     [rsp-8+arg_10], rsi
0x140028132  push    rbp
0x140028133  push    rdi
0x140028134  push    r14
0x140028136  lea     rbp, [rsp-180h]
0x14002813e  sub     rsp, 280h
0x140028145  mov     rax, cs:__security_cookie
0x14002814c  xor     rax, rsp
0x14002814f  mov     [rbp+190h+var_20], rax
0x140028156  mov     rdi, rcx
0x140028159  lea     rdx, [rsp+290h+Filename]; lpFilename
0x14002815e  xor     r14d, r14d
0x140028161  mov     r8d, 104h; nSize
0x140028167  mov     [rcx], r14w
0x14002816b  xor     ecx, ecx; hModule
0x14002816d  movups  xmm0, xmmword ptr cs:aRootsuffix_1; ".rootsuffix"
0x140028174  movups  xmmword ptr [rsp+290h+Source], xmm0
0x140028179  movsd   xmm0, qword ptr cs:aRootsuffix_1+10h; "fix"
0x140028181  movsd   qword ptr [rsp+290h+String1], xmm0
0x140028187  call    cs:__imp_GetModuleFileNameW
0x14002818d  mov     eax, eax
0x14002818f  add     rax, rax
0x140028192  cmp     rax, 222h
0x140028198  jnb     loc_1400282A3
0x14002819e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400281a2  mov     [rsp+rax+290h+Filename], r14w
0x1400281a8  mov     rax, rbx
0x1400281ab  lea     rcx, [rsp+290h+Filename]
0x1400281b0  inc     rax
0x1400281b3  cmp     [rcx+rax*2], r14w
0x1400281b8  jnz     short loc_1400281B0
0x1400281ba  lea     rsi, [rsp+rax*2+290h+String1]
0x1400281bf  mov     rcx, rsi; String1
0x1400281c2  lea     rdx, aExe; ".exe"
0x1400281c9  call    _wcsicmp_0
0x1400281ce  test    eax, eax
0x1400281d0  jz      short loc_1400281FD
0x1400281d2  mov     [rdi], r14w
0x1400281d6  mov     rcx, [rbp+190h+var_20]
0x1400281dd  xor     rcx, rsp; StackCookie
0x1400281e0  call    __security_check_cookie
0x1400281e5  lea     r11, [rsp+290h+var_10]
0x1400281ed  mov     rbx, [r11+28h]
0x1400281f1  mov     rsi, [r11+30h]
0x1400281f5  mov     rsp, r11
0x1400281f8  pop     r14
0x1400281fa  pop     rdi
0x1400281fb  pop     rbp
0x1400281fc  retn
0x1400281fd  lea     rcx, [rsp+290h+Filename]
0x140028202  mov     rax, rbx
0x140028205  inc     rax
0x140028208  cmp     [rcx+rax*2], r14w
0x14002820d  jnz     short loc_140028205
0x14002820f  mov     edx, 115h
0x140028214  lea     r8, [rsp+290h+Source]; Source
0x140028219  sub     rdx, rax; SizeInWords
0x14002821c  mov     rcx, rsi; Destination
0x14002821f  call    wcscpy_s_0
0x140028224  lea     r8, aR; "r"
0x14002822b  mov     [rsp+290h+Stream], r14
0x140028230  lea     rdx, [rsp+290h+Filename]; FileName
0x140028235  lea     rcx, [rsp+290h+Stream]; Stream
0x14002823a  call    cs:__imp__wfopen_s
0x140028240  mov     r8, [rsp+290h+Stream]; Stream
0x140028245  test    r8, r8
0x140028248  jz      short loc_1400281D6
0x14002824a  mov     edx, 104h; BufferCount
0x14002824f  mov     rcx, rdi; Buffer
0x140028252  call    cs:__imp_fgetws
0x140028258  test    rax, rax
0x14002825b  jz      short loc_140028290
0x14002825d  inc     rbx
0x140028260  cmp     [rdi+rbx*2], r14w
0x140028265  jnz     short loc_14002825D
0x140028267  test    rbx, rbx
0x14002826a  jz      short loc_14002827A
0x14002826c  cmp     word ptr [rdi+rbx*2-2], 0Ah
0x140028272  jnz     short loc_14002827A
0x140028274  mov     [rdi+rbx*2-2], r14w
0x14002827a  sub     rbx, 1
0x14002827e  jz      short loc_140028294
0x140028280  cmp     word ptr [rdi+rbx*2-2], 20h ; ' '
0x140028286  jnz     short loc_140028294
0x140028288  mov     [rdi+rbx*2-2], r14w
0x14002828e  jmp     short loc_140028294
0x140028290  mov     [rdi], r14w
0x140028294  mov     rcx, [rsp+290h+Stream]; Stream
0x140028299  call    fclose_0
0x14002829e  jmp     loc_1400281D6
0x1400282a3  call    __report_rangecheckfailure
```
