# KerbInitKernelPackage

- ea: `0x140020c10`
- end: `0x140020cda`
- name: `KerbInitKernelPackage`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140010240`
- `0x140020a50`
- `0x140020c10`
- `0x14002c848`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x140020c7e`
- `ntoskrnl!ExInitializeResourceLite` at `0x140020c95`
- `ntoskrnl!ExInitializeResourceLite` at `0x140020c7e`
- `ntoskrnl!ExInitializeResourceLite` at `0x140020c95`
- `ntoskrnl!ExDeleteResourceLite` at `0x140020cae`
- `ntoskrnl!ExDeleteResourceLite` at `0x140020cae`

## pseudocode

```c
NTSTATUS __fastcall KerbInitKernelPackage(__int128 *a1)
{
  __int128 v1; // xmm0
  __int128 v2; // xmm2
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  NTSTATUS result; // eax
  NTSTATUS v6; // ebx

  v1 = *a1;
  KerbPoolType = PagedPool;
  v2 = a1[1];
  v3 = a1[3];
  KspKernelFunctions = v1;
  v4 = a1[2];
  xmmword_140018CA0 = v2;
  xmmword_140018CB0 = v4;
  qword_140018CD0 = *((_QWORD *)a1 + 8);
  xmmword_140018CC0 = v3;
  KerbPagedList = (void *)((__int64 (__fastcall *)(_QWORD))v2)(0);
  if ( !KerbPagedList )
    return -1073741801;
  result = ExInitializeResourceLite(&KerbGlobalResource);
  if ( result >= 0 )
  {
    v6 = ExInitializeResourceLite(&KerbContextResource);
    if ( v6 >= 0 )
    {
      KerbInitDefaults();
      KerbCryptInitialized = (unsigned int)LibAttach() != 0;
      return 0;
    }
    else
    {
      ExDeleteResourceLite(&KerbGlobalResource);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140020c10  push    rbx
0x140020c12  sub     rsp, 20h
0x140020c16  movups  xmm0, xmmword ptr [rcx]
0x140020c19  mov     cs:?KerbPoolType@@3W4_POOL_TYPE@@A, 1; _POOL_TYPE KerbPoolType
0x140020c23  movups  xmm2, xmmword ptr [rcx+10h]
0x140020c27  movups  xmm1, xmmword ptr [rcx+30h]
0x140020c2b  movaps  xmmword ptr cs:?KspKernelFunctions@@3U_SECPKG_KERNEL_FUNCTIONS@@A, xmm0; _SECPKG_KERNEL_FUNCTIONS KspKernelFunctions
0x140020c32  movq    rax, xmm2
0x140020c37  movups  xmm0, xmmword ptr [rcx+20h]
0x140020c3b  movaps  cs:xmmword_140018CA0, xmm2
0x140020c42  movaps  cs:xmmword_140018CB0, xmm0
0x140020c49  movsd   xmm0, qword ptr [rcx+40h]
0x140020c4e  xor     ecx, ecx
0x140020c50  movsd   cs:qword_140018CD0, xmm0
0x140020c58  movaps  cs:xmmword_140018CC0, xmm1
0x140020c5f  call    _guard_dispatch_icall
0x140020c64  mov     cs:?KerbPagedList@@3PEAXEA, rax; void * KerbPagedList
0x140020c6b  test    rax, rax
0x140020c6e  jnz     short loc_140020C77
0x140020c70  mov     eax, 0C0000017h
0x140020c75  jmp     short loc_140020CD3
0x140020c77  lea     rcx, ?KerbGlobalResource@@3U_ERESOURCE@@A; Resource
0x140020c7e  call    cs:__imp_ExInitializeResourceLite
0x140020c85  nop     dword ptr [rax+rax+00h]
0x140020c8a  test    eax, eax
0x140020c8c  js      short loc_140020CD3
0x140020c8e  lea     rcx, KerbContextResource; Resource
0x140020c95  call    cs:__imp_ExInitializeResourceLite
0x140020c9c  nop     dword ptr [rax+rax+00h]
0x140020ca1  mov     ebx, eax
0x140020ca3  test    eax, eax
0x140020ca5  jns     short loc_140020CBE
0x140020ca7  lea     rcx, ?KerbGlobalResource@@3U_ERESOURCE@@A; Resource
0x140020cae  call    cs:__imp_ExDeleteResourceLite
0x140020cb5  nop     dword ptr [rax+rax+00h]
0x140020cba  mov     eax, ebx
0x140020cbc  jmp     short loc_140020CD3
0x140020cbe  call    KerbInitDefaults
0x140020cc3  call    LibAttach
0x140020cc8  test    eax, eax
0x140020cca  setnz   cs:?KerbCryptInitialized@@3EA; uchar KerbCryptInitialized
0x140020cd1  xor     eax, eax
0x140020cd3  add     rsp, 20h
0x140020cd7  pop     rbx
0x140020cd8  retn
```
