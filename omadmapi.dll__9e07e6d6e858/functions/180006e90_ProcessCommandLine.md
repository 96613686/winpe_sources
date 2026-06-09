# ProcessCommandLine

- ea: `0x180006e90`
- end: `0x1800071c7`
- name: `ProcessCommandLine`
- size: `823`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180006d9c`
- `0x180006e90`
- `0x1800071d0`
- `0x180024010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180006f6e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007066`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000711e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180006f6e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007066`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000711e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000702d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000702d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006fd5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f2b`

## pseudocode

```c
__int64 __fastcall ProcessCommandLine(
        __int64 a1,
        int a2,
        __int64 (__fastcall *a3)(unsigned __int16 *, __int64),
        const unsigned __int16 *a4,
        __int64 a5,
        int a6)
{
  const unsigned __int16 *v6; // rdi
  const unsigned __int16 *v10; // rax
  __int64 v11; // r9
  int v12; // ebx
  unsigned int v13; // ecx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rbp
  unsigned __int16 *v16; // r14
  wchar_t v17; // ax
  __int64 v18; // r12
  wchar_t v19; // dx
  const unsigned __int16 *v20; // r8
  wchar_t v21; // ax
  const unsigned __int16 *v22; // rcx
  const unsigned __int16 *v23; // rsi
  const unsigned __int16 *v24; // rdi
  unsigned __int16 v25; // ax
  unsigned __int16 *v26; // rbx
  const unsigned __int16 *v27; // rcx
  unsigned __int16 *v28; // rsi
  wchar_t v29; // ax
  const unsigned __int16 *v30; // rsi
  const unsigned __int16 *v31; // r15
  const unsigned __int16 *v32; // rcx
  const unsigned __int16 *v33; // rbx
  int v34; // eax
  int v36; // [rsp+70h] [rbp+8h]
  const unsigned __int16 *v38; // [rsp+88h] [rbp+20h] BYREF

  v36 = a1;
  v6 = a4;
  if ( !a4 )
    return (unsigned int)-2147024809;
  v10 = a4;
  v11 = 2147483646;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v12 = -2147024809;
  v13 = v11 == 0 ? 0x80070057 : 0;
  v14 = (2147483646 - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
  if ( !v11 )
    return v13;
  v15 = v14 + 1;
  if ( v14 + 1 < v14 )
  {
    return (unsigned int)-2147024362;
  }
  else if ( (v15 & 0x80000000) != 0LL )
  {
    return (unsigned int)-2102788093;
  }
  else
  {
    v16 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)(2 * v15));
    if ( v16 )
    {
      if ( a1 )
      {
        if ( a2 > 0 )
        {
          v17 = *v6;
          v12 = 0;
          if ( *v6 )
          {
            v18 = a5;
            do
            {
              do
              {
                if ( !(unsigned int)_o_iswspace(v17) )
                  break;
                v17 = *++v6;
              }
              while ( *v6 );
              v19 = *v6;
              if ( *v6 )
              {
                if ( v19 == 34 )
                {
                  v20 = ++v6;
                  v21 = *v6;
                  if ( !*v6 )
                    goto LABEL_22;
                  v22 = v6;
                  v23 = v6;
                  while ( v21 != 34 )
                  {
                    v6 = v22 + 1;
                    v21 = v22[1];
                    v22 = v6;
                    v23 = v6;
                    if ( !v21 )
                      goto LABEL_22;
                  }
                  v12 = StringCchCopyNW(v16, v15, v20, v23 - v20);
                  if ( v12 < 0 )
                    break;
                  v12 = a3(v16, v18);
                  if ( v12 < 0 )
                    break;
                  if ( *v6 )
                    v6 = v23 + 1;
                }
                else if ( wcschr(L"/-", v19) )
                {
                  v24 = v6 + 1;
                  v38 = v24;
                  v25 = *v24;
                  if ( !*v24 )
                    goto LABEL_22;
                  v26 = (unsigned __int16 *)v24;
                  v27 = v24;
                  do
                  {
                    v28 = (unsigned __int16 *)v27;
                    if ( (unsigned int)_o_iswspace(v25) )
                      break;
                    v38 = ++v26;
                    v27 = v26;
                    v28 = v26;
                    v25 = *v26;
                  }
                  while ( *v26 );
                  v12 = StringCchCopyNW(v16, v15, v24, v28 - v24);
                  if ( v12 < 0 )
                    break;
                  v12 = ProcessCommandLineOption(v36, a2, (_DWORD)v16, v18, a6, (__int64)&v38);
                  if ( v12 < 0 )
                    break;
                  v6 = v38;
                }
                else
                {
                  if ( !a3 || (v29 = *v6) == 0 )
                  {
LABEL_22:
                    v12 = -2147467259;
                    break;
                  }
                  v30 = v6;
                  v31 = v6;
                  v32 = v6;
                  do
                  {
                    v33 = v32;
                    if ( (unsigned int)_o_iswspace(v29) )
                      break;
                    v6 = v31 + 1;
                    v29 = v31[1];
                    v31 = v6;
                    v32 = v6;
                    v33 = v6;
                  }
                  while ( v29 );
                  v34 = StringCchCopyNW(v16, v15, v30, v33 - v30);
                  v18 = a5;
                  v12 = v34;
                  if ( v34 < 0 )
                    break;
                  v12 = a3(v16, a5);
                  if ( v12 < 0 )
                    break;
                }
              }
              v17 = *v6;
            }
            while ( *v6 );
          }
        }
      }
      LocalFree(v16);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006e90  mov     [rsp+arg_10], rbx
0x180006e95  mov     [rsp+arg_8], edx
0x180006e99  mov     [rsp+arg_0], rcx
0x180006e9e  push    rbp
0x180006e9f  push    rsi
0x180006ea0  push    rdi
0x180006ea1  push    r12
0x180006ea3  push    r13
0x180006ea5  push    r14
0x180006ea7  push    r15
0x180006ea9  sub     rsp, 30h
0x180006ead  xor     r12d, r12d
0x180006eb0  mov     rdi, r9
0x180006eb3  mov     r13, r8
0x180006eb6  mov     r15d, edx
0x180006eb9  mov     rsi, rcx
0x180006ebc  test    r9, r9
0x180006ebf  jz      loc_1800071A5
0x180006ec5  mov     r10d, 7FFFFFFEh
0x180006ecb  mov     rax, rdi
0x180006ece  mov     r9d, r10d
0x180006ed1  cmp     [rax], r12w
0x180006ed5  jz      short loc_180006EE1
0x180006ed7  add     rax, 2
0x180006edb  sub     r9, 1
0x180006edf  jnz     short loc_180006ED1
0x180006ee1  mov     rax, r9
0x180006ee4  mov     ebx, 80070057h
0x180006ee9  neg     rax
0x180006eec  mov     rax, r9
0x180006eef  sbb     ecx, ecx
0x180006ef1  sub     r10, r9
0x180006ef4  not     ecx
0x180006ef6  and     ecx, ebx
0x180006ef8  neg     rax
0x180006efb  sbb     rdx, rdx
0x180006efe  and     rdx, r10
0x180006f01  test    r9, r9
0x180006f04  jz      loc_1800071AA
0x180006f0a  lea     rbp, [rdx+1]
0x180006f0e  cmp     rbp, rdx
0x180006f11  jb      loc_18000719E
0x180006f17  test    ebp, ebp
0x180006f19  js      loc_180007197
0x180006f1f  lea     edx, ds:0[rbp*2]; uBytes
0x180006f26  mov     ecx, 40h ; '@'; uFlags
0x180006f2b  call    cs:__imp_LocalAlloc
0x180006f32  nop     dword ptr [rax+rax+00h]
0x180006f37  mov     r14, rax
0x180006f3a  test    rax, rax
0x180006f3d  jnz     short loc_180006F49
0x180006f3f  mov     ebx, 8007000Eh
0x180006f44  jmp     loc_1800071AC
0x180006f49  test    rsi, rsi
0x180006f4c  jz      loc_180006FD2
0x180006f52  xor     esi, esi
0x180006f54  test    r15d, r15d
0x180006f57  jle     short loc_180006FD2
0x180006f59  movzx   eax, word ptr [rdi]
0x180006f5c  mov     ebx, esi
0x180006f5e  test    ax, ax
0x180006f61  jz      short loc_180006FD2
0x180006f63  mov     r12, [rsp+68h+arg_20]
0x180006f6b  movzx   ecx, ax
0x180006f6e  call    cs:__imp__o_iswspace
0x180006f75  nop     dword ptr [rax+rax+00h]
0x180006f7a  test    eax, eax
0x180006f7c  jz      short loc_180006F8A
0x180006f7e  add     rdi, 2
0x180006f82  movzx   eax, word ptr [rdi]
0x180006f85  test    ax, ax
0x180006f88  jnz     short loc_180006F6B
0x180006f8a  movzx   edx, word ptr [rdi]; Ch
0x180006f8d  test    dx, dx
0x180006f90  jz      loc_180007186
0x180006f96  cmp     dx, 22h ; '"'
0x180006f9a  jnz     loc_180007026
0x180006fa0  add     rdi, 2
0x180006fa4  mov     r8, rdi; unsigned __int16 *
0x180006fa7  movzx   eax, word ptr [rdi]
0x180006faa  test    ax, ax
0x180006fad  jz      short loc_180006FCD
0x180006faf  mov     rcx, rdi
0x180006fb2  mov     rsi, rdi
0x180006fb5  cmp     ax, 22h ; '"'
0x180006fb9  jz      short loc_180006FE6
0x180006fbb  lea     rdi, [rcx+2]
0x180006fbf  movzx   eax, word ptr [rdi]
0x180006fc2  mov     rcx, rdi
0x180006fc5  mov     rsi, rdi
0x180006fc8  test    ax, ax
0x180006fcb  jnz     short loc_180006FB5
0x180006fcd  mov     ebx, 80004005h
0x180006fd2  mov     rcx, r14; hMem
0x180006fd5  call    cs:__imp_LocalFree
0x180006fdc  nop     dword ptr [rax+rax+00h]
0x180006fe1  jmp     loc_1800071AC
0x180006fe6  mov     r9, rsi
0x180006fe9  mov     rdx, rbp; unsigned __int64
0x180006fec  sub     r9, r8
0x180006fef  mov     rcx, r14; unsigned __int16 *
0x180006ff2  sar     r9, 1; unsigned __int64
0x180006ff5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180006ffa  mov     ebx, eax
0x180006ffc  test    eax, eax
0x180006ffe  js      short loc_180006FD2
0x180007000  mov     rdx, r12
0x180007003  mov     rcx, r14
0x180007006  mov     rax, r13
0x180007009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000700e  mov     ebx, eax
0x180007010  xor     eax, eax
0x180007012  test    ebx, ebx
0x180007014  js      short loc_180006FD2
0x180007016  cmp     [rdi], ax
0x180007019  jz      short loc_18000701F
0x18000701b  lea     rdi, [rsi+2]
0x18000701f  xor     esi, esi
0x180007021  jmp     loc_180007186
0x180007026  lea     rcx, Str; "/-"
0x18000702d  call    cs:__imp_wcschr
0x180007034  nop     dword ptr [rax+rax+00h]
0x180007039  test    rax, rax
0x18000703c  jz      loc_1800070FA
0x180007042  add     rdi, 2
0x180007046  mov     [rsp+68h+arg_18], rdi
0x18000704e  movzx   eax, word ptr [rdi]
0x180007051  test    ax, ax
0x180007054  jz      loc_180006FCD
0x18000705a  mov     rbx, rdi
0x18000705d  mov     rcx, rdi
0x180007060  mov     rsi, rcx
0x180007063  movzx   ecx, ax
0x180007066  call    cs:__imp__o_iswspace
0x18000706d  nop     dword ptr [rax+rax+00h]
0x180007072  test    eax, eax
0x180007074  jnz     short loc_180007090
0x180007076  add     rbx, 2
0x18000707a  mov     [rsp+68h+arg_18], rbx
0x180007082  mov     rcx, rbx
0x180007085  mov     rsi, rbx
0x180007088  movzx   eax, word ptr [rbx]
0x18000708b  test    ax, ax
0x18000708e  jnz     short loc_180007060
0x180007090  sub     rsi, rdi
0x180007093  mov     r8, rdi; unsigned __int16 *
0x180007096  sar     rsi, 1
0x180007099  mov     rdx, rbp; unsigned __int64
0x18000709c  mov     r9, rsi; unsigned __int64
0x18000709f  mov     rcx, r14; unsigned __int16 *
0x1800070a2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800070a7  mov     r15d, [rsp+68h+arg_8]
0x1800070ac  xor     esi, esi
0x1800070ae  mov     ebx, eax
0x1800070b0  test    eax, eax
0x1800070b2  js      loc_180006FD2
0x1800070b8  mov     rcx, [rsp+68h+arg_0]
0x1800070bd  lea     rax, [rsp+68h+arg_18]
0x1800070c5  mov     [rsp+68h+var_40], rax
0x1800070ca  mov     r9, r12
0x1800070cd  mov     eax, [rsp+68h+arg_28]
0x1800070d4  mov     r8, r14
0x1800070d7  mov     edx, r15d
0x1800070da  mov     [rsp+68h+var_48], eax
0x1800070de  call    ProcessCommandLineOption
0x1800070e3  mov     ebx, eax
0x1800070e5  test    eax, eax
0x1800070e7  js      loc_180006FD2
0x1800070ed  mov     rdi, [rsp+68h+arg_18]
0x1800070f5  jmp     loc_180007186
0x1800070fa  test    r13, r13
0x1800070fd  jz      loc_180006FCD
0x180007103  movzx   eax, word ptr [rdi]
0x180007106  test    ax, ax
0x180007109  jz      loc_180006FCD
0x18000710f  mov     rsi, rdi
0x180007112  mov     r15, rdi
0x180007115  mov     rcx, rdi
0x180007118  mov     rbx, rcx
0x18000711b  movzx   ecx, ax
0x18000711e  call    cs:__imp__o_iswspace
0x180007125  nop     dword ptr [rax+rax+00h]
0x18000712a  test    eax, eax
0x18000712c  jnz     short loc_180007143
0x18000712e  lea     rdi, [r15+2]
0x180007132  movzx   eax, word ptr [rdi]
0x180007135  mov     r15, rdi
0x180007138  mov     rcx, rdi
0x18000713b  mov     rbx, rdi
0x18000713e  test    ax, ax
0x180007141  jnz     short loc_180007118
0x180007143  sub     rbx, rsi
0x180007146  mov     r8, rsi; unsigned __int16 *
0x180007149  sar     rbx, 1
0x18000714c  mov     rdx, rbp; unsigned __int64
0x18000714f  mov     r9, rbx; unsigned __int64
0x180007152  mov     rcx, r14; unsigned __int16 *
0x180007155  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000715a  mov     r12, [rsp+68h+arg_20]
0x180007162  xor     esi, esi
0x180007164  mov     ebx, eax
0x180007166  test    eax, eax
0x180007168  js      loc_180006FD2
0x18000716e  mov     rdx, r12
0x180007171  mov     rcx, r14
0x180007174  mov     rax, r13
0x180007177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717c  mov     ebx, eax
0x18000717e  test    eax, eax
0x180007180  js      loc_180006FD2
0x180007186  movzx   eax, word ptr [rdi]
0x180007189  test    ax, ax
0x18000718c  jnz     loc_180006F6B
0x180007192  jmp     loc_180006FD2
0x180007197  mov     ebx, 82AA0003h
0x18000719c  jmp     short loc_1800071AC
0x18000719e  mov     ebx, 80070216h
0x1800071a3  jmp     short loc_1800071AC
0x1800071a5  mov     ecx, 80070057h
0x1800071aa  mov     ebx, ecx
0x1800071ac  mov     eax, ebx
0x1800071ae  mov     rbx, [rsp+68h+arg_10]
0x1800071b6  add     rsp, 30h
0x1800071ba  pop     r15
0x1800071bc  pop     r14
0x1800071be  pop     r13
0x1800071c0  pop     r12
0x1800071c2  pop     rdi
0x1800071c3  pop     rsi
0x1800071c4  pop     rbp
0x1800071c5  retn
```
