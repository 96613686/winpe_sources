# NtProcessStartup_AfterSecurityCookieInitialized

- ea: `0x140001030`
- end: `0x140001415`
- name: `NtProcessStartup_AfterSecurityCookieInitialized`
- size: `997`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140001010`

## callees

- `0x140001030`
- `0x14000169c`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x1400011b0`
- `ntdll!NtTerminateProcess` at `0x1400011b0`
- `ntdll!isspace` at `0x14000129e`
- `ntdll!isspace` at `0x1400012fd`
- `ntdll!isspace` at `0x14000138a`
- `ntdll!isspace` at `0x1400013de`
- `ntdll!isspace` at `0x14000129e`
- `ntdll!isspace` at `0x1400012fd`
- `ntdll!isspace` at `0x14000138a`
- `ntdll!isspace` at `0x1400013de`
- `ntdll!RtlFreeAnsiString` at `0x14000117e`
- `ntdll!RtlFreeAnsiString` at `0x1400011e8`
- `ntdll!RtlFreeAnsiString` at `0x14000117e`
- `ntdll!RtlFreeAnsiString` at `0x1400011e8`
- `ntdll!RtlAllocateHeap` at `0x140001124`
- `ntdll!RtlAllocateHeap` at `0x140001124`
- `ntdll!RtlNormalizeProcessParams` at `0x140001056`
- `ntdll!RtlNormalizeProcessParams` at `0x140001056`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x140001258`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x140001258`

## pseudocode

```c
NTSTATUS __fastcall NtProcessStartup_AfterSecurityCookieInitialized(__int64 a1)
{
  struct _RTL_USER_PROCESS_PARAMETERS *v2; // rcx
  NTSTATUS v3; // r12d
  const char **v4; // rsi
  PRTL_USER_PROCESS_PARAMETERS v5; // r13
  const UNICODE_STRING *p_CommandLine; // rdx
  unsigned int DebugFlags; // ebx
  __int64 v8; // rsi
  unsigned int v9; // ebp
  char *v10; // r14
  int v11; // r15d
  char *Buffer; // r8
  unsigned __int16 Length; // r9
  _WORD *Environment; // rcx
  int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rbx
  SIZE_T v18; // rsi
  char **Heap; // rax
  char **v20; // rdi
  _QWORD *v21; // rdx
  _WORD *v22; // rax
  char *v25; // rbx
  char *v27; // rbx
  char *v28; // rbp
  char *v29; // rsi
  struct _STRING AnsiString; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v31; // [rsp+80h] [rbp+8h]
  unsigned int v32; // [rsp+80h] [rbp+8h]
  int argc; // [rsp+88h] [rbp+10h]
  __int64 v34; // [rsp+90h] [rbp+18h] BYREF
  char **argv; // [rsp+98h] [rbp+20h]

  v2 = *(struct _RTL_USER_PROCESS_PARAMETERS **)(a1 + 32);
  v3 = 0;
  v34 = 0;
  AnsiString = 0;
  argc = 0;
  v4 = (const char **)&v34;
  v5 = RtlNormalizeProcessParams(v2);
  argv = (char **)&v34;
  if ( !v5 )
  {
    RtlFreeAnsiString(&AnsiString);
LABEL_20:
    v3 = main(argc, (const char **)argv, v4);
    return NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v3);
  }
  p_CommandLine = &v5->CommandLine;
  DebugFlags = v5->DebugFlags;
  v8 = 0;
  v9 = 1;
  v31 = DebugFlags;
  if ( v5->CommandLine.Buffer && p_CommandLine->Length
    || (p_CommandLine = &v5->ImagePathName, v10 = 0, v11 = 0, v5->ImagePathName.Buffer) )
  {
    v3 = RtlUnicodeStringToAnsiString(&AnsiString, p_CommandLine, 1u);
    if ( v3 < 0 )
      goto LABEL_18;
    Length = AnsiString.Length;
    Buffer = AnsiString.Buffer;
    v11 = AnsiString.Length;
    v10 = AnsiString.Buffer;
    if ( !AnsiString.Length )
      goto LABEL_5;
    do
    {
      if ( !*v10 || !v11 )
        break;
      while ( *v10 && isspace(*v10) )
      {
        ++v10;
        if ( !--v11 )
        {
          DebugFlags = v31;
          goto LABEL_4;
        }
      }
      if ( !*v10 )
        break;
      ++v9;
      v25 = v10;
      do
      {
        ++v10;
        --v11;
      }
      while ( v11 && !isspace(*v10) );
      v8 += v10 - v25 + 1;
    }
    while ( v11 );
    DebugFlags = v31;
  }
LABEL_4:
  Buffer = AnsiString.Buffer;
  Length = AnsiString.Length;
LABEL_5:
  Environment = v5->Environment;
  v15 = 0;
  v32 = DebugFlags;
  if ( Environment && *Environment )
  {
    do
    {
      ++Environment;
      ++v15;
      while ( *Environment++ )
        ;
    }
    while ( *Environment );
  }
  v16 = v9 + v15 + 1;
  if ( (unsigned int)v16 <= 2 )
    goto LABEL_18;
  if ( v9 > 1 )
  {
    v10 = Buffer;
    v11 = Length;
  }
  v17 = v16;
  v18 = 8 * v16 + v8;
  Heap = (char **)RtlAllocateHeap(*(PVOID *)(a1 + 48), 0, v18);
  v20 = Heap;
  if ( !Heap )
  {
    DebugFlags = v32;
    v3 = -1073741801;
LABEL_18:
    v4 = (const char **)&v34;
    goto LABEL_13;
  }
  argv = Heap;
  if ( v9 > 1 )
  {
    v27 = (char *)&Heap[v17];
    v28 = (char *)Heap + v18;
    while ( v11 )
    {
      if ( !*v10 || v27 >= v28 )
        break;
      while ( *v10 && isspace(*v10) )
      {
        ++v10;
        if ( !--v11 )
          goto LABEL_11;
      }
      if ( *v10 )
      {
        *v20++ = v27;
        ++argc;
        do
        {
          v29 = v27;
          *v27++ = *v10++;
          if ( !--v11 )
            break;
          if ( v27 >= v28 )
            goto LABEL_61;
        }
        while ( !isspace(*v10) );
        if ( v27 < v28 )
        {
          *v27++ = 0;
          continue;
        }
LABEL_61:
        v27 = v29;
        *v29 = 0;
      }
    }
  }
LABEL_11:
  DebugFlags = v32;
  v4 = (const char **)(v20 + 1);
  *v20 = 0;
  v21 = v20 + 1;
  v22 = v5->Environment;
  if ( v22 && *v22 )
  {
    do
    {
      *v21++ = v22++;
      while ( *v22++ )
        ;
    }
    while ( *v22 );
  }
  *v21 = 0;
LABEL_13:
  RtlFreeAnsiString(&AnsiString);
  if ( DebugFlags )
    __debugbreak();
  if ( v3 >= 0 )
    goto LABEL_20;
  return NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v3);
}

```

## disassembly

```asm
0x140001030  push    rbx
0x140001032  push    rsi
0x140001033  push    rdi
0x140001034  push    r12
0x140001036  push    r13
0x140001038  sub     rsp, 50h
0x14000103c  mov     rdi, rcx
0x14000103f  xorps   xmm0, xmm0
0x140001042  mov     rcx, [rcx+20h]; ProcessParameters
0x140001046  xor     r12d, r12d
0x140001049  mov     [rsp+78h+arg_10], r12
0x140001051  movups  xmmword ptr [rsp+78h+AnsiString.Length], xmm0
0x140001056  call    cs:__imp_RtlNormalizeProcessParams
0x14000105d  nop     dword ptr [rax+rax+00h]
0x140001062  mov     [rsp+78h+argc], r12d
0x14000106a  lea     rsi, [rsp+78h+arg_10]
0x140001072  mov     r13, rax
0x140001075  lea     rax, [rsp+78h+arg_10]
0x14000107d  mov     [rsp+78h+argv], rax
0x140001085  test    r13, r13
0x140001088  jz      loc_1400011E0
0x14000108e  lea     rdx, [r13+70h]; SourceString
0x140001092  mov     ebx, [r13+0Ch]
0x140001096  mov     esi, r12d
0x140001099  mov     [rsp+78h+var_30], rbp
0x14000109e  mov     ebp, 1
0x1400010a3  mov     [rsp+78h+var_38], r14
0x1400010a8  mov     [rsp+78h+var_40], r15
0x1400010ad  mov     [rsp+78h+arg_0], ebx
0x1400010b4  cmp     [rdx+8], r12
0x1400010b8  jnz     loc_140001246
0x1400010be  lea     rdx, [r13+60h]
0x1400010c2  mov     r14, r12
0x1400010c5  mov     r15d, r12d
0x1400010c8  cmp     [rdx+8], rsi
0x1400010cc  jnz     loc_14000124F
0x1400010d2  mov     r8, [rsp+78h+AnsiString.Buffer]
0x1400010d7  movzx   r9d, [rsp+78h+AnsiString.Length]
0x1400010dd  mov     rcx, [r13+80h]
0x1400010e4  xor     edx, edx
0x1400010e6  mov     [rsp+78h+arg_0], ebx
0x1400010ed  test    rcx, rcx
0x1400010f0  jnz     loc_14000130F
0x1400010f6  lea     eax, [rdx+1]
0x1400010f9  add     eax, ebp
0x1400010fb  cmp     eax, 2
0x1400010fe  jbe     loc_1400011D6
0x140001104  cmp     ebp, 1
0x140001107  jbe     short loc_140001110
0x140001109  mov     r14, r8
0x14000110c  movzx   r15d, r9w
0x140001110  mov     rcx, [rdi+30h]; HeapHandle
0x140001114  lea     rbx, ds:0[rax*8]
0x14000111c  add     rsi, rbx
0x14000111f  xor     edx, edx; Flags
0x140001121  mov     r8, rsi; Size
0x140001124  call    cs:__imp_RtlAllocateHeap
0x14000112b  nop     dword ptr [rax+rax+00h]
0x140001130  mov     rdi, rax
0x140001133  test    rax, rax
0x140001136  jz      loc_1400011C9
0x14000113c  mov     [rsp+78h+argv], rax
0x140001144  cmp     ebp, 1
0x140001147  ja      loc_140001346
0x14000114d  mov     ebx, [rsp+78h+arg_0]
0x140001154  lea     rsi, [rdi+8]
0x140001158  mov     qword ptr [rdi], 0
0x14000115f  mov     rdx, rsi
0x140001162  mov     rax, [r13+80h]
0x140001169  test    rax, rax
0x14000116c  jnz     loc_140001213
0x140001172  mov     qword ptr [rdx], 0
0x140001179  lea     rcx, [rsp+78h+AnsiString]; AnsiString
0x14000117e  call    cs:__imp_RtlFreeAnsiString
0x140001185  nop     dword ptr [rax+rax+00h]
0x14000118a  mov     r15, [rsp+78h+var_40]
0x14000118f  mov     r14, [rsp+78h+var_38]
0x140001194  mov     rbp, [rsp+78h+var_30]
0x140001199  test    ebx, ebx
0x14000119b  jnz     loc_14000140F
0x1400011a1  test    r12d, r12d
0x1400011a4  jns     short loc_1400011F4
0x1400011a6  mov     edx, r12d; ExitStatus
0x1400011a9  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400011b0  call    cs:__imp_NtTerminateProcess
0x1400011b7  nop     dword ptr [rax+rax+00h]
0x1400011bc  add     rsp, 50h
0x1400011c0  pop     r13
0x1400011c2  pop     r12
0x1400011c4  pop     rdi
0x1400011c5  pop     rsi
0x1400011c6  pop     rbx
0x1400011c7  retn
0x1400011c9  mov     ebx, [rsp+78h+arg_0]
0x1400011d0  mov     r12d, 0C0000017h
0x1400011d6  lea     rsi, [rsp+78h+arg_10]
0x1400011de  jmp     short loc_140001179
0x1400011e0  lea     rcx, [rsp+78h+AnsiString]; AnsiString
0x1400011e5  mov     ebx, r12d
0x1400011e8  call    cs:__imp_RtlFreeAnsiString
0x1400011ef  nop     dword ptr [rax+rax+00h]
0x1400011f4  mov     rdx, [rsp+78h+argv]; argv
0x1400011fc  mov     r9d, ebx
0x1400011ff  mov     ecx, [rsp+78h+argc]; argc
0x140001206  mov     r8, rsi; envp
0x140001209  call    main
0x14000120e  mov     r12d, eax
0x140001211  jmp     short loc_1400011A6
0x140001213  cmp     word ptr [rax], 0
0x140001217  jz      loc_140001172
0x14000121d  nop     dword ptr [rax]
0x140001220  mov     [rdx], rax
0x140001223  add     rdx, 8
0x140001227  add     rax, 2
0x14000122b  nop     dword ptr [rax+rax+00h]
0x140001230  movzx   ecx, word ptr [rax]
0x140001233  add     rax, 2
0x140001237  test    cx, cx
0x14000123a  jnz     short loc_140001230
0x14000123c  cmp     [rax], cx
0x14000123f  jnz     short loc_140001220
0x140001241  jmp     loc_140001172
0x140001246  cmp     [rdx], si
0x140001249  jz      loc_1400010BE
0x14000124f  movzx   r8d, bpl; AllocateDestinationString
0x140001253  lea     rcx, [rsp+78h+AnsiString]; DestinationString
0x140001258  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14000125f  nop     dword ptr [rax+rax+00h]
0x140001264  mov     r12d, eax
0x140001267  test    eax, eax
0x140001269  js      loc_1400011D6
0x14000126f  movzx   r9d, [rsp+78h+AnsiString.Length]
0x140001275  mov     r8, [rsp+78h+AnsiString.Buffer]
0x14000127a  mov     r15d, r9d
0x14000127d  mov     r14, r8
0x140001280  test    r9d, r9d
0x140001283  jz      loc_1400010DD
0x140001289  cmp     byte ptr [r14], 0
0x14000128d  jz      short loc_1400012D4
0x14000128f  test    r15d, r15d
0x140001292  jz      short loc_1400012D4
0x140001294  movsx   eax, byte ptr [r14]
0x140001298  test    al, al
0x14000129a  jz      short loc_1400012E0
0x14000129c  mov     ecx, eax; C
0x14000129e  call    cs:__imp_isspace
0x1400012a5  nop     dword ptr [rax+rax+00h]
0x1400012aa  test    eax, eax
0x1400012ac  jz      short loc_1400012E0
0x1400012ae  inc     r14
0x1400012b1  add     r15d, 0FFFFFFFFh
0x1400012b5  jnz     short loc_140001294
0x1400012b7  mov     ebx, [rsp+78h+arg_0]
0x1400012be  jmp     loc_1400010D2
0x1400012c3  inc     rsi
0x1400012c6  mov     rax, r14
0x1400012c9  sub     rax, rbx
0x1400012cc  add     rsi, rax
0x1400012cf  test    r15d, r15d
0x1400012d2  jnz     short loc_140001289
0x1400012d4  mov     ebx, [rsp+78h+arg_0]
0x1400012db  jmp     loc_1400010D2
0x1400012e0  cmp     byte ptr [r14], 0
0x1400012e4  jz      short loc_1400012D4
0x1400012e6  inc     ebp
0x1400012e8  mov     rbx, r14
0x1400012eb  nop     dword ptr [rax+rax+00h]
0x1400012f0  inc     r14
0x1400012f3  add     r15d, 0FFFFFFFFh
0x1400012f7  jz      short loc_1400012C3
0x1400012f9  movsx   ecx, byte ptr [r14]; C
0x1400012fd  call    cs:__imp_isspace
0x140001304  nop     dword ptr [rax+rax+00h]
0x140001309  test    eax, eax
0x14000130b  jz      short loc_1400012F0
0x14000130d  jmp     short loc_1400012C3
0x14000130f  cmp     [rcx], dx
0x140001312  jz      loc_1400010F6
0x140001318  nop     dword ptr [rax+rax+00000000h]
0x140001320  add     rcx, 2
0x140001324  inc     edx
0x140001326  nop     word ptr [rax+rax+00000000h]
0x140001330  movzx   eax, word ptr [rcx]
0x140001333  add     rcx, 2
0x140001337  test    ax, ax
0x14000133a  jnz     short loc_140001330
0x14000133c  cmp     [rcx], ax
0x14000133f  jnz     short loc_140001320
0x140001341  jmp     loc_1400010F6
0x140001346  add     rbx, rax
0x140001349  lea     rbp, [rsi+rax]
0x14000134d  test    r15d, r15d
0x140001350  jz      loc_14000114D
0x140001356  mov     eax, [rsp+78h+arg_0]
0x14000135d  mov     [rsp+78h+arg_0], eax
0x140001364  cmp     byte ptr [r14], 0
0x140001368  jz      loc_14000114D
0x14000136e  cmp     rbx, rbp
0x140001371  jnb     loc_14000114D
0x140001377  test    r15d, r15d
0x14000137a  jz      loc_14000114D
0x140001380  movsx   eax, byte ptr [r14]
0x140001384  test    al, al
0x140001386  jz      short loc_1400013AC
0x140001388  mov     ecx, eax; C
0x14000138a  call    cs:__imp_isspace
0x140001391  nop     dword ptr [rax+rax+00h]
0x140001396  test    eax, eax
0x140001398  jz      short loc_1400013AC
0x14000139a  inc     r14
0x14000139d  add     r15d, 0FFFFFFFFh
0x1400013a1  jnz     short loc_140001380
0x1400013a3  test    r15d, r15d
0x1400013a6  jz      loc_14000114D
0x1400013ac  cmp     byte ptr [r14], 0
0x1400013b0  jz      short loc_140001401
0x1400013b2  mov     [rdi], rbx
0x1400013b5  add     rdi, 8
0x1400013b9  inc     [rsp+78h+argc]
0x1400013c0  movzx   eax, byte ptr [r14]
0x1400013c4  mov     rsi, rbx
0x1400013c7  mov     [rbx], al
0x1400013c9  inc     r14
0x1400013cc  inc     rbx
0x1400013cf  add     r15d, 0FFFFFFFFh
0x1400013d3  jz      short loc_1400013EE
0x1400013d5  cmp     rbx, rbp
0x1400013d8  jnb     short loc_1400013FB
0x1400013da  movsx   ecx, byte ptr [r14]; C
0x1400013de  call    cs:__imp_isspace
0x1400013e5  nop     dword ptr [rax+rax+00h]
0x1400013ea  test    eax, eax
0x1400013ec  jz      short loc_1400013C0
0x1400013ee  cmp     rbx, rbp
0x1400013f1  jnb     short loc_1400013FB
0x1400013f3  mov     byte ptr [rbx], 0
0x1400013f6  inc     rbx
0x1400013f9  jmp     short loc_140001401
0x1400013fb  mov     rbx, rsi
0x1400013fe  mov     byte ptr [rsi], 0
0x140001401  test    r15d, r15d
0x140001404  jz      loc_14000114D
0x14000140a  jmp     loc_140001364
0x14000140f  int     3; Trap to Debugger
0x140001410  jmp     loc_1400011A1
```
