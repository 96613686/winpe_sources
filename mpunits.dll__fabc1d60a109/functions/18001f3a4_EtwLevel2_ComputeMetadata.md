# EtwLevel2_ComputeMetadata

- ea: `0x18001f3a4`
- end: `0x18001f722`
- name: `EtwLevel2_ComputeMetadata`
- size: `894`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18001fba0`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x18001f3a4`
- `0x18001f728`
- `0x180020778`
- `0x180043e08`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18001f43a`
- `msvcrt!malloc` at `0x18001f4af`
- `msvcrt!malloc` at `0x18001f510`
- `msvcrt!malloc` at `0x18001f43a`
- `msvcrt!malloc` at `0x18001f4af`
- `msvcrt!malloc` at `0x18001f510`
- `msvcrt!free` at `0x18001f5cf`
- `msvcrt!free` at `0x18001f6c5`
- `msvcrt!free` at `0x18001f6cd`
- `msvcrt!free` at `0x18001f6d7`
- `msvcrt!free` at `0x18001f5cf`
- `msvcrt!free` at `0x18001f6c5`
- `msvcrt!free` at `0x18001f6cd`
- `msvcrt!free` at `0x18001f6d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001f670`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001f670`
- `miutils!Class_New` at `0x18001f492`
- `miutils!Class_New` at `0x18001f492`
- `tdh!TdhGetEventInformation` at `0x18001f427`
- `tdh!TdhGetEventInformation` at `0x18001f468`
- `tdh!TdhGetEventInformation` at `0x18001f427`
- `tdh!TdhGetEventInformation` at `0x18001f468`

## string_xrefs

- `0x18001f665`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall EtwLevel2_ComputeMetadata(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  TRACE_EVENT_INFO *v6; // r13
  unsigned int v7; // r12d
  __int64 TopLevelPropertyCount; // rbx
  void *v9; // rax
  void *v10; // r12
  char *v11; // rax
  char *v12; // rbx
  unsigned int v13; // r8d
  __int64 v14; // rdx
  __int64 v15; // rax
  HMODULE ModuleHandleA; // rax
  PULONG BufferSize; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+30h] [rbp-D0h]
  int v21; // [rsp+38h] [rbp-C8h]
  int v22; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+48h] [rbp-B8h]
  int v24; // [rsp+50h] [rbp-B0h]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+68h] [rbp-98h]
  ULONG v28; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  __int128 v32; // [rsp+90h] [rbp-70h]
  void *Block; // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v34)(); // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t pszDest[80]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = a1[28];
  v34 = Locator_Fixed;
  *(_QWORD *)&v32 = v3;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  Block = 0;
  v35 = 0;
  v6 = 0;
  v31 = 16;
  v36 = 0;
  if ( TdhGetEventInformation((PEVENT_RECORD)v3, 0, 0, 0, &v28) != 122 )
    goto LABEL_9;
  v6 = (TRACE_EVENT_INFO *)malloc(v28);
  if ( !v6 )
    goto LABEL_3;
  if ( TdhGetEventInformation((PEVENT_RECORD)v3, 0, 0, v6, &v28) )
  {
LABEL_9:
    v7 = 1;
    v27 = *(unsigned __int8 *)(v3 + 39);
    v26 = *(unsigned __int8 *)(v3 + 38);
    v25 = *(unsigned __int8 *)(v3 + 37);
    v24 = *(unsigned __int8 *)(v3 + 36);
    v23 = *(unsigned __int8 *)(v3 + 35);
    v22 = *(unsigned __int8 *)(v3 + 34);
    v21 = *(unsigned __int8 *)(v3 + 33);
    v20 = *(unsigned __int8 *)(v3 + 32);
    v19 = *(unsigned __int16 *)(v3 + 30);
    LODWORD(BufferSize) = *(unsigned __int16 *)(v3 + 28);
    StringCchPrintfW(
      pszDest,
      0x50u,
      L"{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
      *(unsigned int *)(v32 + 24),
      BufferSize,
      v19,
      v20,
      v21,
      v22,
      v23,
      v24,
      v25,
      v26,
      v27);
    v32 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v32 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2031, pszDest);
    BYTE8(v32) = 1;
    MI_ReportErrorDetails_ForCustomError(11, (int)L"ETW Normalizer", 0, 0);
    goto LABEL_10;
  }
  TopLevelPropertyCount = (int)v6->TopLevelPropertyCount;
  v7 = Class_New(&MSFT_ETWEventPayload_rtti, 0, 0, 0, &v30);
  if ( v7 )
    goto LABEL_10;
  v9 = malloc(80LL * v6->PropertyCount);
  Block = v9;
  v10 = v9;
  if ( v9 )
  {
    EtwLevel2_ComputeStructure(
      (_DWORD)a1,
      (_DWORD)v9,
      (unsigned int)&v31,
      (unsigned int)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v29,
      (__int64)v6,
      v30,
      0,
      TopLevelPropertyCount);
    v11 = (char *)malloc(v31 + 88);
    v12 = v11;
    if ( v11 )
    {
      *((_QWORD *)v11 + 2) = 2;
      *(_OWORD *)(v11 + 24) = *(_OWORD *)(v3 + 24);
      v13 = *(unsigned __int16 *)(v3 + 40);
      *((_WORD *)v11 + 20) = v13;
      v11[42] = *(_BYTE *)(v3 + 42);
      *((_QWORD *)v11 + 9) = v30;
      *((_QWORD *)v11 + 8) = v29;
      v14 = v29[1];
      *((_QWORD *)v11 + 10) = v11 + 88;
      *((_QWORD *)v11 + 6) = v14;
      *((_QWORD *)v11 + 7) = v10;
      *((_QWORD *)v11 + 12) = v31;
      *((_QWORD *)v11 + 1) = *((_QWORD *)v11 + 3) ^ v13;
      HashMap_Insert(a3, v11);
      **((_QWORD **)v12 + 10) = a1;
      a1[8] = off_1800493D0;
      a1[9] = *((_QWORD *)v12 + 6);
      a1[31] = *((_QWORD *)v12 + 10);
      v15 = *((_QWORD *)v12 + 7);
      a1[34] |= 2uLL;
      a1[33] = v15;
      a1[32] = v12;
      free(v6);
      return 0;
    }
  }
LABEL_3:
  v7 = 27;
LABEL_10:
  free(v6);
  free(0);
  free(Block);
  if ( v29 )
  {
    if ( *v29 )
      (*(void (**)(void))(*v29 + 96LL))();
  }
  return v7;
}

```

## disassembly

```asm
0x18001f3a4  mov     [rsp-8+arg_8], rbx
0x18001f3a9  push    rbp
0x18001f3aa  push    rsi
0x18001f3ab  push    rdi
0x18001f3ac  push    r12
0x18001f3ae  push    r13
0x18001f3b0  push    r14
0x18001f3b2  push    r15
0x18001f3b4  lea     rbp, [rsp-70h]
0x18001f3b9  sub     rsp, 170h
0x18001f3c0  mov     rax, cs:__security_cookie
0x18001f3c7  xor     rax, rsp
0x18001f3ca  mov     [rbp+0A0h+var_40], rax
0x18001f3ce  mov     r14, [rcx+0E0h]
0x18001f3d5  lea     rax, Locator_Fixed
0x18001f3dc  xor     r15d, r15d
0x18001f3df  mov     [rbp+0A0h+var_F8], rax
0x18001f3e3  lea     rax, [rsp+1A0h+var_130]
0x18001f3e8  mov     qword ptr [rbp+0A0h+var_110], r14
0x18001f3ec  mov     rsi, r8
0x18001f3ef  mov     [rsp+1A0h+BufferSize], rax; BufferSize
0x18001f3f4  mov     rdi, rcx
0x18001f3f7  mov     [rsp+1A0h+var_130], r15d
0x18001f3fc  xor     r9d, r9d; Buffer
0x18001f3ff  mov     [rsp+1A0h+var_128], r15
0x18001f404  xor     r8d, r8d; TdhContext
0x18001f407  mov     [rbp+0A0h+var_120], r15
0x18001f40b  xor     edx, edx; TdhContextCount
0x18001f40d  mov     [rbp+0A0h+Block], r15
0x18001f411  mov     rcx, r14; Event
0x18001f414  mov     [rbp+0A0h+var_F0], r15
0x18001f418  mov     r13d, r15d
0x18001f41b  mov     [rbp+0A0h+var_118], 10h
0x18001f423  mov     [rbp+0A0h+var_E8], r15
0x18001f427  call    cs:__imp_TdhGetEventInformation
0x18001f42d  cmp     eax, 7Ah ; 'z'
0x18001f430  jnz     loc_18001F5DC
0x18001f436  mov     ecx, [rsp+1A0h+var_130]; Size
0x18001f43a  call    cs:__imp_malloc
0x18001f440  mov     r13, rax
0x18001f443  test    rax, rax
0x18001f446  jnz     short loc_18001F453
0x18001f448  mov     r12d, 1Bh
0x18001f44e  jmp     loc_18001F6C2
0x18001f453  lea     rax, [rsp+1A0h+var_130]
0x18001f458  mov     r9, r13; Buffer
0x18001f45b  xor     r8d, r8d; TdhContext
0x18001f45e  mov     [rsp+1A0h+BufferSize], rax; BufferSize
0x18001f463  xor     edx, edx; TdhContextCount
0x18001f465  mov     rcx, r14; Event
0x18001f468  call    cs:__imp_TdhGetEventInformation
0x18001f46e  test    eax, eax
0x18001f470  jnz     loc_18001F5DC
0x18001f476  movsxd  rbx, dword ptr [r13+68h]
0x18001f47a  lea     rax, [rbp+0A0h+var_120]
0x18001f47e  xor     r9d, r9d
0x18001f481  mov     [rsp+1A0h+BufferSize], rax
0x18001f486  xor     r8d, r8d
0x18001f489  lea     rcx, MSFT_ETWEventPayload_rtti
0x18001f490  xor     edx, edx
0x18001f492  call    cs:__imp_Class_New
0x18001f498  mov     r12d, eax
0x18001f49b  test    eax, eax
0x18001f49d  jnz     loc_18001F6C2
0x18001f4a3  mov     eax, [r13+64h]
0x18001f4a7  lea     rcx, [rax+rax*4]
0x18001f4ab  shl     rcx, 4; Size
0x18001f4af  call    cs:__imp_malloc
0x18001f4b5  mov     [rbp+0A0h+Block], rax
0x18001f4b9  mov     r12, rax
0x18001f4bc  test    rax, rax
0x18001f4bf  jz      short loc_18001F448
0x18001f4c1  mov     rax, [rbp+0A0h+var_120]
0x18001f4c5  lea     r9, [rbp+0A0h+var_E8]
0x18001f4c9  mov     [rsp+1A0h+var_150], rbx
0x18001f4ce  lea     r8, [rbp+0A0h+var_118]
0x18001f4d2  mov     [rsp+1A0h+var_158], r15
0x18001f4d7  mov     rdx, r12
0x18001f4da  mov     [rsp+1A0h+var_160], rax
0x18001f4df  mov     rcx, rdi
0x18001f4e2  mov     [rsp+1A0h+var_168], r13
0x18001f4e7  lea     rax, [rsp+1A0h+var_128]
0x18001f4ec  mov     [rsp+1A0h+var_170], rax
0x18001f4f1  lea     rax, [rbp+0A0h+var_F8]
0x18001f4f5  mov     [rsp+1A0h+var_178], rax
0x18001f4fa  lea     rax, [rbp+0A0h+var_F0]
0x18001f4fe  mov     [rsp+1A0h+BufferSize], rax
0x18001f503  call    EtwLevel2_ComputeStructure
0x18001f508  mov     rcx, [rbp+0A0h+var_118]
0x18001f50c  add     rcx, 58h ; 'X'; Size
0x18001f510  call    cs:__imp_malloc
0x18001f516  mov     rbx, rax
0x18001f519  test    rax, rax
0x18001f51c  jz      loc_18001F448
0x18001f522  mov     qword ptr [rax+10h], 2
0x18001f52a  mov     rcx, rsi
0x18001f52d  movups  xmm0, xmmword ptr [r14+18h]
0x18001f532  movdqu  xmmword ptr [rax+18h], xmm0
0x18001f537  movzx   r8d, word ptr [r14+28h]
0x18001f53c  mov     [rax+28h], r8w
0x18001f541  mov     al, [r14+2Ah]
0x18001f545  mov     [rbx+2Ah], al
0x18001f548  mov     rax, [rbp+0A0h+var_120]
0x18001f54c  mov     [rbx+48h], rax
0x18001f550  mov     rax, [rsp+1A0h+var_128]
0x18001f555  mov     [rbx+40h], rax
0x18001f559  mov     rax, [rsp+1A0h+var_128]
0x18001f55e  mov     rdx, [rax+8]
0x18001f562  lea     rax, [rbx+58h]
0x18001f566  mov     [rbx+50h], rax
0x18001f56a  mov     [rbx+30h], rdx
0x18001f56e  mov     rdx, rbx
0x18001f571  mov     [rbx+38h], r12
0x18001f575  mov     rax, [rbp+0A0h+var_118]
0x18001f579  mov     [rbx+60h], rax
0x18001f57d  mov     eax, r8d
0x18001f580  xor     rax, [rbx+18h]
0x18001f584  mov     [rbx+8], rax
0x18001f588  call    HashMap_Insert
0x18001f58d  mov     rax, [rbx+50h]
0x18001f591  mov     rcx, r13; Block
0x18001f594  mov     [rax], rdi
0x18001f597  lea     rax, off_1800493D0
0x18001f59e  mov     [rdi+40h], rax
0x18001f5a2  mov     rax, [rbx+30h]
0x18001f5a6  mov     [rdi+48h], rax
0x18001f5aa  mov     rax, [rbx+50h]
0x18001f5ae  mov     [rdi+0F8h], rax
0x18001f5b5  mov     rax, [rbx+38h]
0x18001f5b9  or      qword ptr [rdi+110h], 2
0x18001f5c1  mov     [rdi+108h], rax
0x18001f5c8  mov     [rdi+100h], rbx
0x18001f5cf  call    cs:__imp_free
0x18001f5d5  xor     eax, eax
0x18001f5d7  jmp     loc_18001F6FB
0x18001f5dc  movzx   ecx, byte ptr [r14+26h]
0x18001f5e1  mov     r12d, 1
0x18001f5e7  movzx   edx, byte ptr [r14+25h]
0x18001f5ec  movzx   r8d, byte ptr [r14+24h]
0x18001f5f1  movzx   eax, byte ptr [r14+27h]
0x18001f5f6  movzx   r10d, byte ptr [r14+23h]
0x18001f5fb  movzx   r11d, byte ptr [r14+22h]
0x18001f600  movzx   ebx, byte ptr [r14+21h]
0x18001f605  movzx   edi, byte ptr [r14+20h]
0x18001f60a  movzx   esi, word ptr [r14+1Eh]
0x18001f60f  mov     r9, qword ptr [rbp+0A0h+var_110]
0x18001f613  movzx   r15d, word ptr [r14+28h]
0x18001f618  movzx   r14d, word ptr [r14+1Ch]
0x18001f61d  mov     [rsp+1A0h+var_138], eax
0x18001f621  mov     r9d, [r9+18h]
0x18001f625  mov     [rsp+1A0h+var_140], ecx
0x18001f629  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x18001f62d  mov     [rsp+1A0h+var_148], edx
0x18001f631  lea     edx, [r12+4Fh]; cchDest
0x18001f636  mov     dword ptr [rsp+1A0h+var_150], r8d
0x18001f63b  lea     r8, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x18001f642  mov     dword ptr [rsp+1A0h+var_158], r10d
0x18001f647  mov     dword ptr [rsp+1A0h+var_160], r11d
0x18001f64c  mov     dword ptr [rsp+1A0h+var_168], ebx
0x18001f650  mov     dword ptr [rsp+1A0h+var_170], edi
0x18001f654  mov     dword ptr [rsp+1A0h+var_178], esi
0x18001f658  mov     dword ptr [rsp+1A0h+BufferSize], r14d
0x18001f65d  call    StringCchPrintfW
0x18001f662  xorps   xmm0, xmm0
0x18001f665  lea     rcx, ModuleName; "mpunits.dll"
0x18001f66c  movups  [rbp+0A0h+var_110], xmm0
0x18001f670  call    cs:__imp_GetModuleHandleA
0x18001f676  mov     r9d, r15d
0x18001f679  lea     r8, [rbp+0A0h+pszDest]
0x18001f67d  mov     rcx, rax
0x18001f680  mov     edx, 7EFh
0x18001f685  call    _Intlstr_FormatString_FormatMessage
0x18001f68a  mov     qword ptr [rbp+0A0h+var_110], rax
0x18001f68e  lea     r9, [rbp+0A0h+var_110]
0x18001f692  mov     byte ptr [rbp+0A0h+var_110+8], r12b
0x18001f696  lea     r8d, [r12+9]
0x18001f69b  movaps  xmm0, [rbp+0A0h+var_110]
0x18001f69f  lea     rdx, aEtwNormalizer; "ETW Normalizer"
0x18001f6a6  xor     r15d, r15d
0x18001f6a9  movdqa  [rbp+0A0h+var_110], xmm0
0x18001f6ae  mov     [rsp+1A0h+var_178], r15; __int64
0x18001f6b3  lea     ecx, [r12+0Ah]; int
0x18001f6b8  mov     [rsp+1A0h+BufferSize], r15; __int64
0x18001f6bd  call    MI_ReportErrorDetails_ForCustomError
0x18001f6c2  mov     rcx, r13; Block
0x18001f6c5  call    cs:__imp_free
0x18001f6cb  xor     ecx, ecx; Block
0x18001f6cd  call    cs:__imp_free
0x18001f6d3  mov     rcx, [rbp+0A0h+Block]; Block
0x18001f6d7  call    cs:__imp_free
0x18001f6dd  mov     rcx, [rsp+1A0h+var_128]
0x18001f6e2  test    rcx, rcx
0x18001f6e5  jz      short loc_18001F6F8
0x18001f6e7  mov     rax, [rcx]
0x18001f6ea  test    rax, rax
0x18001f6ed  jz      short loc_18001F6F8
0x18001f6ef  mov     rax, [rax+60h]
0x18001f6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6f8  mov     eax, r12d
0x18001f6fb  mov     rcx, [rbp+0A0h+var_40]
0x18001f6ff  xor     rcx, rsp; StackCookie
0x18001f702  call    __security_check_cookie
0x18001f707  mov     rbx, [rsp+1A0h+arg_8]
0x18001f70f  add     rsp, 170h
0x18001f716  pop     r15
0x18001f718  pop     r14
0x18001f71a  pop     r13
0x18001f71c  pop     r12
0x18001f71e  pop     rdi
0x18001f71f  pop     rsi
0x18001f720  pop     rbp
0x18001f721  retn
```
