# GenAllocateModuleObject(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ushort *,unsigned __int64,ulong,_INTERNAL_MODULE * *)

- ea: `0x180017b8c`
- end: `0x180018323`
- name: `?GenAllocateModuleObject@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAG_KKPEAPEAU_INTERNAL_MODULE@@@Z`
- size: `1943`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, unsigned __int16 *, unsigned __int64, unsigned int, struct _INTERNAL_MODULE **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18001ad48`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180016b74`
- `0x180016f50`
- `0x180017b8c`
- `0x18001a3f0`
- `0x18001acf0`
- `0x18001bca0`
- `0x18001bec8`
- `0x18001bf10`
- `0x18001cdb0`
- `0x180026cb4`
- `0x18002c010`

## string_xrefs

- `0x180017ef4`: `GenAllocateModuleObject.GenImageNtHeader(0x%I64x, %ws) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall GenAllocateModuleObject(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned int a5,
        struct _INTERNAL_MODULE **a6)
{
  char *v9; // rdi
  __int64 v11; // rax
  int v12; // r15d
  void *v13; // rax
  _QWORD *v14; // r13
  int v15; // edx
  struct _INTERNAL_PROCESS *v16; // rdx
  unsigned int v17; // ebx
  int v18; // r8d
  _QWORD *v19; // r15
  __int64 v20; // r10
  unsigned __int16 *PathTail; // rax
  unsigned __int8 v22; // al
  struct _INTERNAL_PROCESS *v23; // r14
  void *v24; // rdx
  char **v25; // r14
  unsigned int *v26; // r12
  void *v27; // rdx
  _QWORD *v28; // r12
  void *v29; // [rsp+20h] [rbp-258h]
  unsigned __int8 *v30; // [rsp+20h] [rbp-258h]
  void **v31; // [rsp+28h] [rbp-250h]
  unsigned __int8 v32; // [rsp+60h] [rbp-218h] BYREF
  unsigned int v33; // [rsp+64h] [rbp-214h] BYREF
  void *v34; // [rsp+68h] [rbp-210h]
  struct _INTERNAL_PROCESS *v35; // [rsp+70h] [rbp-208h]
  unsigned int v36; // [rsp+78h] [rbp-200h] BYREF
  unsigned int VirtualAddress; // [rsp+7Ch] [rbp-1FCh]
  _DWORD v38[14]; // [rsp+80h] [rbp-1F8h] BYREF
  char *v39; // [rsp+B8h] [rbp-1C0h]
  struct _INTERNAL_MODULE **v40; // [rsp+C0h] [rbp-1B8h]
  char *v41; // [rsp+D0h] [rbp-1A8h]
  struct _MINIDUMP_STATE *v42; // [rsp+E0h] [rbp-198h]
  struct _INTERNAL_PROCESS *v43; // [rsp+F0h] [rbp-188h]
  unsigned __int16 *v44; // [rsp+F8h] [rbp-180h]
  unsigned __int64 v45; // [rsp+100h] [rbp-178h]
  _QWORD *v46; // [rsp+108h] [rbp-170h]
  char *v47; // [rsp+110h] [rbp-168h]
  struct _IMAGE_NT_HEADERS64 v48; // [rsp+120h] [rbp-158h] BYREF

  v35 = a2;
  v42 = a1;
  v43 = a2;
  v44 = a3;
  v45 = a4;
  v40 = a6;
  v34 = 0;
  v36 = 0;
  v32 = 0;
  v38[0] = 0;
  VirtualAddress = 0;
  v9 = (char *)AllocMemory(a1, 0xA8u);
  v41 = v9;
  if ( !v9 )
    return 2147942414LL;
  v11 = -1;
  do
    ++v11;
  while ( a3[v11] );
  v12 = v11 + 1;
  if ( (unsigned int)(v11 + 1) <= 0x168 )
    v12 = 360;
  v13 = AllocMemory(a1, 2 * v12);
  v39 = v9 + 120;
  *((_QWORD *)v9 + 15) = v13;
  if ( !v13 )
  {
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v9);
    return 2147942414LL;
  }
  v14 = (_QWORD *)((char *)a1 + 16);
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, unsigned __int64, char *))(**((_QWORD **)a1 + 2)
                                                                                                + 120LL))(
          *((_QWORD *)a1 + 2),
          *(_QWORD *)a1,
          a3,
          a4,
          v9 + 28);
  if ( v15 )
  {
    *(_OWORD *)(v9 + 28) = 0;
    *(_OWORD *)(v9 + 44) = 0;
    *(_OWORD *)(v9 + 60) = 0;
    *((_DWORD *)v9 + 19) = 0;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      8,
      "GenAllocateModuleObject.GetVersion(0x%I64x, %ws) failed, 0x%08x",
      a4,
      a3,
      v15);
  }
  LODWORD(v29) = v12;
  v33 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)*v14 + 96LL))(
          *v14,
          a3,
          &v36,
          *((_QWORD *)v9 + 15));
  if ( !v33 && VerifyMapping(a1, v16, a3, v34, (unsigned __int64)v29, a4) )
  {
    v19 = v9 + 120;
  }
  else
  {
    v34 = 0;
    v31 = (void **)v38;
    v30 = &v32;
    v33 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, unsigned __int64))(*(_QWORD *)*v14 + 112LL))(
            *v14,
            *(_QWORD *)a1,
            a3,
            a4);
    if ( v33 )
    {
      *((_DWORD *)a1 + 44) |= 4u;
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), *((_QWORD *)v9 + 15));
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v9);
      v17 = v33;
      LODWORD(v31) = v33;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "GenAllocateModuleObject.GetImageHeaderInfo(0x%I64x, %ws) failed, 0x%08x",
        a4,
        a3,
        v31);
      return v17;
    }
    v18 = v12;
    v19 = v9 + 120;
    GenStrCopyNW(*((unsigned __int16 **)v9 + 15), a3, v18);
  }
  v46 = v19;
  v47 = (char *)a1 + 16;
  v20 = *((_QWORD *)v9 + 15);
  if ( *((char *)a1 + 56) >= 0 )
    PathTail = (unsigned __int16 *)*((_QWORD *)v9 + 15);
  else
    PathTail = GenGetPathTail(*((unsigned __int16 **)v9 + 15));
  *((_QWORD *)v9 + 16) = PathTail;
  *((_QWORD *)v9 + 1) = a4;
  *((_DWORD *)v9 + 34) = a5;
  *((_QWORD *)v9 + 10) = 0;
  *((_DWORD *)v9 + 22) = 0;
  *((_QWORD *)v9 + 12) = 0;
  *((_DWORD *)v9 + 26) = 0;
  if ( v34 )
  {
    memset_0(&v48, 0, sizeof(v48));
    if ( !GenImageNtHeader(v34, &v48) )
    {
      (*(void (__fastcall **)(_QWORD, void *))(**((_QWORD **)a1 + 2) + 104LL))(*((_QWORD *)a1 + 2), v34);
      *((_DWORD *)a1 + 44) |= 4u;
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), *((_QWORD *)v9 + 15));
      (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v9);
      LODWORD(v31) = v33;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "GenAllocateModuleObject.GenImageNtHeader(0x%I64x, %ws) failed, 0x%08x",
        a4,
        a3,
        v31);
      return 2147943554LL;
    }
    *((_WORD *)v9 + 80) = v48.OptionalHeader.DllCharacteristics;
    if ( (*((_DWORD *)a1 + 14) & 0x80000) != 0 )
      GenAddModuleHeaders(a1, v35, a4, &v48, v34, a3);
    v22 = 4;
    if ( v48.OptionalHeader.Magic == 523 )
      v22 = 8;
    v32 = v22;
    v38[0] = v48.FileHeader.Machine;
    *((_DWORD *)v9 + 4) = v48.OptionalHeader.SizeOfImage;
    *((_DWORD *)v9 + 5) = v48.OptionalHeader.CheckSum;
    *((_DWORD *)v9 + 6) = v48.FileHeader.TimeDateStamp;
    if ( v48.OptionalHeader.NumberOfRvaAndSizes > 9 && v48.OptionalHeader.DataDirectory[9].Size )
      VirtualAddress = v48.OptionalHeader.DataDirectory[9].VirtualAddress;
    if ( (v9[136] & 8) != 0 )
      GenGetDebugRecord(a1, (char *)v34, v36, 2, (unsigned int)v30, (void **)v9 + 10, (unsigned int *)v9 + 22);
    if ( (v9[136] & 4) != 0 )
      GenGetDebugRecord(a1, (char *)v34, v36, 4, (unsigned int)v30, (void **)v9 + 12, (unsigned int *)v9 + 26);
    v38[8] = 0;
    (*(void (__fastcall **)(_QWORD, void *))(*(_QWORD *)*v14 + 104LL))(*v14, v34);
  }
  else
  {
    v33 = 0;
    v23 = v35;
    if ( (a5 & 8) != 0 )
    {
      LODWORD(v30) = 2;
      if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64, unsigned __int64, unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)*v14 + 128LL))(
              *v14,
              *((_QWORD *)v35 + 8),
              v20,
              a4,
              v30,
              0,
              &v33)
        && v33 <= 0x2800 )
      {
        v24 = AllocMemory(a1, v33);
        v25 = (char **)(v9 + 80);
        *((_QWORD *)v9 + 10) = v24;
        if ( v24 )
        {
          v26 = (unsigned int *)(v9 + 88);
          *((_DWORD *)v9 + 22) = v33;
          if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, void *, char *))(*(_QWORD *)*v14 + 128LL))(
                 *v14,
                 *((_QWORD *)v35 + 8),
                 *v19,
                 *((_QWORD *)v9 + 1),
                 2,
                 v24,
                 v9 + 88) )
          {
            (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), *v25);
            *v25 = 0;
            *v26 = 0;
          }
          else if ( (*((_DWORD *)a1 + 14) & 0x100000) != 0 )
          {
            GenUpdatePdbNameInCvRecord(*v25, *v26, 1);
          }
        }
        v23 = v35;
      }
    }
    v33 = 0;
    if ( (v9[136] & 4) != 0 )
    {
      LODWORD(v30) = 2;
      if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned __int8 *, _QWORD, unsigned int *))(*(_QWORD *)*v14 + 128LL))(
              *v14,
              *((_QWORD *)v23 + 8),
              *v19,
              *((_QWORD *)v9 + 1),
              v30,
              0,
              &v33)
        && v33 <= 0x2800 )
      {
        v27 = AllocMemory(a1, v33);
        v28 = v9 + 96;
        *((_QWORD *)v9 + 12) = v27;
        if ( v27 )
        {
          *((_DWORD *)v9 + 26) = v33;
          if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int, void *, char *))(*(_QWORD *)*v14 + 128LL))(
                 *v14,
                 *((_QWORD *)v23 + 8),
                 *v19,
                 *((_QWORD *)v9 + 1),
                 4,
                 v27,
                 v9 + 104) )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), *v28);
            *v28 = 0;
            *((_DWORD *)v9 + 26) = 0;
          }
        }
      }
    }
  }
  if ( VirtualAddress )
    GenReadTlsDirectory(a1, v35, (struct _INTERNAL_MODULE *)v9, v32, VirtualAddress);
  *v40 = (struct _INTERNAL_MODULE *)v9;
  return 0;
}

```

## disassembly

```asm
0x180017b8c  push    rbx
0x180017b8e  push    rsi
0x180017b8f  push    rdi
0x180017b90  push    r12
0x180017b92  push    r13
0x180017b94  push    r14
0x180017b96  push    r15
0x180017b98  sub     rsp, 240h
0x180017b9f  mov     rax, cs:__security_cookie
0x180017ba6  xor     rax, rsp
0x180017ba9  mov     [rsp+278h+var_48], rax
0x180017bb1  mov     r12, r9
0x180017bb4  mov     r14, r8
0x180017bb7  mov     [rsp+278h+var_208], rdx
0x180017bbc  mov     rsi, rcx
0x180017bbf  mov     [rsp+278h+var_198], rcx
0x180017bc7  mov     [rsp+278h+var_188], rdx
0x180017bcf  mov     [rsp+278h+var_180], r8
0x180017bd7  mov     [rsp+278h+var_178], r9
0x180017bdf  mov     rax, [rsp+278h+arg_28]
0x180017be7  mov     [rsp+278h+var_1B8], rax
0x180017bef  xor     ebx, ebx
0x180017bf1  mov     [rsp+278h+var_210], rbx
0x180017bf6  mov     [rsp+278h+var_200], ebx
0x180017bfa  mov     [rsp+278h+var_218], bl
0x180017bfe  mov     [rsp+278h+var_1F8], ebx
0x180017c05  mov     [rsp+278h+var_1FC], ebx
0x180017c09  mov     edx, 0A8h; unsigned int
0x180017c0e  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x180017c13  mov     rdi, rax
0x180017c16  mov     [rsp+278h+var_1A8], rax
0x180017c1e  test    rax, rax
0x180017c21  jnz     short loc_180017C2D
0x180017c23  mov     eax, 8007000Eh
0x180017c28  jmp     loc_180018300
0x180017c2d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017c31  inc     rax
0x180017c34  cmp     [r14+rax*2], bx
0x180017c39  jnz     short loc_180017C31
0x180017c3b  lea     r15d, [rax+1]
0x180017c3f  mov     eax, 168h
0x180017c44  cmp     r15d, eax
0x180017c47  cmovbe  r15d, eax
0x180017c4b  lea     edx, [r15+r15]; unsigned int
0x180017c4f  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x180017c52  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x180017c57  lea     rcx, [rdi+78h]
0x180017c5b  mov     [rsp+278h+var_1C0], rcx
0x180017c63  mov     [rcx], rax
0x180017c66  test    rax, rax
0x180017c69  jnz     short loc_180017C80
0x180017c6b  mov     rcx, [rsi+20h]
0x180017c6f  mov     rax, [rcx]
0x180017c72  mov     rdx, rdi
0x180017c75  mov     rax, [rax+18h]
0x180017c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c7e  jmp     short loc_180017C23
0x180017c80  lea     r13, [rsi+10h]
0x180017c84  mov     rcx, [r13+0]
0x180017c88  lea     rdx, [rdi+1Ch]
0x180017c8c  mov     rax, [rcx]
0x180017c8f  mov     [rsp+278h+var_258], rdx
0x180017c94  mov     r9, r12
0x180017c97  mov     r8, r14
0x180017c9a  mov     rdx, [rsi]
0x180017c9d  mov     rax, [rax+78h]
0x180017ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ca6  mov     edx, eax
0x180017ca8  test    eax, eax
0x180017caa  jz      short loc_180017CEB
0x180017cac  xorps   xmm0, xmm0
0x180017caf  xor     ecx, ecx
0x180017cb1  movups  xmmword ptr [rdi+1Ch], xmm0
0x180017cb5  movups  xmmword ptr [rdi+2Ch], xmm0
0x180017cb9  movups  xmmword ptr [rdi+3Ch], xmm0
0x180017cbd  mov     [rdi+4Ch], ecx
0x180017cc0  mov     r10, [rsi+28h]
0x180017cc4  mov     rcx, [r10]
0x180017cc7  mov     rax, [rcx+8]
0x180017ccb  mov     dword ptr [rsp+278h+var_250], edx
0x180017ccf  mov     [rsp+278h+var_258], r14
0x180017cd4  mov     r9, r12
0x180017cd7  lea     r8, aGenallocatemod_0; "GenAllocateModuleObject.GetVersion(0x%I"...
0x180017cde  mov     edx, 8
0x180017ce3  mov     rcx, r10
0x180017ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ceb  mov     rcx, [r13+0]
0x180017cef  mov     rax, [rcx]
0x180017cf2  lea     rdx, [rsp+278h+var_210]
0x180017cf7  mov     [rsp+278h+var_250], rdx
0x180017cfc  mov     dword ptr [rsp+278h+var_258], r15d; unsigned __int64
0x180017d01  mov     r9, [rdi+78h]
0x180017d05  lea     r8, [rsp+278h+var_200]
0x180017d0a  mov     rdx, r14
0x180017d0d  mov     rax, [rax+60h]
0x180017d11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d16  mov     [rsp+278h+var_214], eax
0x180017d1a  test    eax, eax
0x180017d1c  jnz     short loc_180017D3B
0x180017d1e  mov     [rsp+278h+var_250], r12; unsigned __int64
0x180017d23  mov     r9, [rsp+278h+var_210]; void *
0x180017d28  mov     r8, r14; unsigned __int16 *
0x180017d2b  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x180017d2e  call    ?VerifyMapping@@YA_NPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAGPEAX_K4@Z; VerifyMapping(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ushort *,void *,unsigned __int64,unsigned __int64)
0x180017d33  test    al, al
0x180017d35  jnz     loc_180017E12
0x180017d3b  mov     [rsp+278h+var_210], rbx
0x180017d40  mov     rcx, [r13+0]
0x180017d44  mov     rax, [rcx]
0x180017d47  lea     rdx, [rdi+18h]
0x180017d4b  lea     r8, [rdi+14h]
0x180017d4f  lea     r9, [rdi+10h]
0x180017d53  lea     r10, [rsp+278h+var_1FC]
0x180017d58  mov     [rsp+278h+var_230], r10
0x180017d5d  mov     [rsp+278h+var_238], rdx
0x180017d62  mov     [rsp+278h+var_240], r8
0x180017d67  mov     [rsp+278h+var_248], r9
0x180017d6c  lea     rdx, [rsp+278h+var_1F8]
0x180017d74  mov     [rsp+278h+var_250], rdx
0x180017d79  lea     rdx, [rsp+278h+var_218]
0x180017d7e  mov     [rsp+278h+var_258], rdx
0x180017d83  mov     r9, r12
0x180017d86  mov     r8, r14
0x180017d89  mov     rdx, [rsi]
0x180017d8c  mov     rax, [rax+70h]
0x180017d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d95  mov     [rsp+278h+var_214], eax
0x180017d99  test    eax, eax
0x180017d9b  jz      short loc_180017DFE
0x180017d9d  or      dword ptr [rsi+0B0h], 4
0x180017da4  mov     rcx, [rsi+20h]
0x180017da8  mov     rax, [rcx]
0x180017dab  mov     rdx, [rdi+78h]
0x180017daf  mov     rax, [rax+18h]
0x180017db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017db8  mov     rcx, [rsi+20h]
0x180017dbc  mov     rax, [rcx]
0x180017dbf  mov     rdx, rdi
0x180017dc2  mov     rax, [rax+18h]
0x180017dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dcb  mov     rcx, [rsi+28h]
0x180017dcf  mov     rax, [rcx]
0x180017dd2  mov     ebx, [rsp+278h+var_214]
0x180017dd6  mov     dword ptr [rsp+278h+var_250], ebx
0x180017dda  mov     [rsp+278h+var_258], r14
0x180017ddf  mov     r9, r12
0x180017de2  lea     r8, aGenallocatemod; "GenAllocateModuleObject.GetImageHeaderI"...
0x180017de9  mov     edx, 4
0x180017dee  mov     rax, [rax+8]
0x180017df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017df7  mov     eax, ebx
0x180017df9  jmp     loc_180018300
0x180017dfe  mov     r8d, r15d; int
0x180017e01  mov     rdx, r14; unsigned __int16 *
0x180017e04  lea     r15, [rdi+78h]
0x180017e08  mov     rcx, [r15]; unsigned __int16 *
0x180017e0b  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x180017e10  jmp     short loc_180017E16
0x180017e12  lea     r15, [rdi+78h]
0x180017e16  mov     [rsp+278h+var_170], r15
0x180017e1e  mov     [rsp+278h+var_168], r13
0x180017e26  mov     r10, [rdi+78h]
0x180017e2a  test    byte ptr [rsi+38h], 80h
0x180017e2e  jz      short loc_180017E3A
0x180017e30  mov     rcx, r10; unsigned __int16 *
0x180017e33  call    ?GenGetPathTail@@YAPEAGPEAG@Z; GenGetPathTail(ushort *)
0x180017e38  jmp     short loc_180017E3D
0x180017e3a  mov     rax, r10
0x180017e3d  mov     [rdi+80h], rax
0x180017e44  mov     [rdi+8], r12
0x180017e48  mov     eax, [rsp+278h+arg_20]
0x180017e4f  mov     [rdi+88h], eax
0x180017e55  mov     [rdi+50h], rbx
0x180017e59  mov     [rdi+58h], ebx
0x180017e5c  mov     [rdi+60h], rbx
0x180017e60  mov     [rdi+68h], ebx
0x180017e63  cmp     [rsp+278h+var_210], rbx
0x180017e68  jz      loc_180018106
0x180017e6e  xor     edx, edx; Val
0x180017e70  mov     r8d, 108h; Size
0x180017e76  lea     rcx, [rsp+278h+var_158]; void *
0x180017e7e  call    memset_0
0x180017e83  lea     rdx, [rsp+278h+var_158]; struct _IMAGE_NT_HEADERS64 *
0x180017e8b  mov     rcx, [rsp+278h+var_210]; void *
0x180017e90  call    ?GenImageNtHeader@@YAPEAU_IMAGE_NT_HEADERS64@@PEAXPEAU1@@Z; GenImageNtHeader(void *,_IMAGE_NT_HEADERS64 *)
0x180017e95  test    rax, rax
0x180017e98  jnz     short loc_180017F13
0x180017e9a  mov     rcx, [rsi+10h]
0x180017e9e  mov     rax, [rcx]
0x180017ea1  mov     rdx, [rsp+278h+var_210]
0x180017ea6  mov     rax, [rax+68h]
0x180017eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eaf  or      dword ptr [rsi+0B0h], 4
0x180017eb6  mov     rcx, [rsi+20h]
0x180017eba  mov     rax, [rcx]
0x180017ebd  mov     rdx, [rdi+78h]
0x180017ec1  mov     rax, [rax+18h]
0x180017ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eca  mov     rcx, [rsi+20h]
0x180017ece  mov     rax, [rcx]
0x180017ed1  mov     rdx, rdi
0x180017ed4  mov     rax, [rax+18h]
0x180017ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017edd  mov     rcx, [rsi+28h]
0x180017ee1  mov     rax, [rcx]
0x180017ee4  mov     ebx, [rsp+278h+var_214]
0x180017ee8  mov     dword ptr [rsp+278h+var_250], ebx
0x180017eec  mov     [rsp+278h+var_258], r14
0x180017ef1  mov     r9, r12
0x180017ef4  lea     r8, aGenallocatemod_2; "GenAllocateModuleObject.GenImageNtHeade"...
0x180017efb  mov     edx, 4
0x180017f00  mov     rax, [rax+8]
0x180017f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f09  mov     eax, 80070482h
0x180017f0e  jmp     loc_180018300
0x180017f13  movzx   eax, [rsp+278h+var_158.OptionalHeader.DllCharacteristics]
0x180017f1b  mov     [rdi+0A0h], ax
0x180017f22  test    dword ptr [rsi+38h], 80000h
0x180017f29  jz      short loc_180017F52
0x180017f2b  mov     [rsp+278h+var_250], r14; unsigned __int16 *
0x180017f30  mov     rax, [rsp+278h+var_210]
0x180017f35  mov     [rsp+278h+var_258], rax; unsigned int
0x180017f3a  lea     r9, [rsp+278h+var_158]; struct _IMAGE_NT_HEADERS64 *
0x180017f42  mov     r8, r12; unsigned __int64
0x180017f45  mov     rdx, [rsp+278h+var_208]; struct _INTERNAL_PROCESS *
0x180017f4a  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x180017f4d  call    ?GenAddModuleHeaders@@YAXPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@_KPEAU_IMAGE_NT_HEADERS64@@PEAXPEBG@Z; GenAddModuleHeaders(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,unsigned __int64,_IMAGE_NT_HEADERS64 *,void *,ushort const *)
0x180017f52  mov     eax, 4
0x180017f57  mov     ecx, 20Bh
0x180017f5c  cmp     [rsp+278h+var_158.OptionalHeader.Magic], cx
0x180017f64  lea     ecx, [rax+4]
0x180017f67  cmovz   eax, ecx
0x180017f6a  mov     [rsp+278h+var_218], al
0x180017f6e  movzx   eax, [rsp+278h+var_158.FileHeader.Machine]
0x180017f76  mov     [rsp+278h+var_1F8], eax
0x180017f7d  mov     eax, [rsp+278h+var_158.OptionalHeader.SizeOfImage]
0x180017f84  mov     [rdi+10h], eax
0x180017f87  mov     eax, [rsp+278h+var_158.OptionalHeader.CheckSum]
0x180017f8e  mov     [rdi+14h], eax
0x180017f91  mov     eax, [rsp+278h+var_158.FileHeader.TimeDateStamp]
0x180017f98  mov     [rdi+18h], eax
0x180017f9b  cmp     [rsp+278h+var_158.OptionalHeader.NumberOfRvaAndSizes], 9
0x180017fa3  jbe     short loc_180017FB9
0x180017fa5  cmp     [rsp+278h+var_158.OptionalHeader.DataDirectory.Size+48h], ebx
0x180017fac  jbe     short loc_180017FB9
0x180017fae  mov     eax, [rsp+278h+var_158.OptionalHeader.DataDirectory.VirtualAddress+48h]
0x180017fb5  mov     [rsp+278h+var_1FC], eax
0x180017fb9  test    [rdi+88h], cl
0x180017fbf  jz      short loc_180017FEB
0x180017fc1  lea     rax, [rdi+58h]
0x180017fc5  mov     [rsp+278h+var_248], rax; unsigned int *
0x180017fca  lea     rax, [rdi+50h]
0x180017fce  mov     [rsp+278h+var_250], rax; void **
0x180017fd3  mov     r9d, 2; unsigned int
0x180017fd9  mov     r8d, [rsp+278h+var_200]; unsigned int
0x180017fde  mov     rdx, [rsp+278h+var_210]; void *
0x180017fe3  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x180017fe6  call    ?GenGetDebugRecord@@YAJPEAU_MINIDUMP_STATE@@PEAXKKKPEAPEAXPEAK@Z; GenGetDebugRecord(_MINIDUMP_STATE *,void *,ulong,ulong,ulong,void * *,ulong *)
0x180017feb  test    byte ptr [rdi+88h], 4
0x180017ff2  jz      short loc_18001801E
0x180017ff4  lea     rax, [rdi+68h]
0x180017ff8  mov     [rsp+278h+var_248], rax; unsigned int *
0x180017ffd  lea     rax, [rdi+60h]
0x180018001  mov     [rsp+278h+var_250], rax; void **
0x180018006  mov     r9d, 4; unsigned int
0x18001800c  mov     r8d, [rsp+278h+var_200]; unsigned int
0x180018011  mov     rdx, [rsp+278h+var_210]; void *
0x180018016  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x180018019  call    ?GenGetDebugRecord@@YAJPEAU_MINIDUMP_STATE@@PEAXKKKPEAPEAXPEAK@Z; GenGetDebugRecord(_MINIDUMP_STATE *,void *,ulong,ulong,ulong,void * *,ulong *)
0x18001801e  mov     r15d, ebx
0x180018021  mov     [rsp+278h+var_1D8], ebx
0x180018028  jmp     short loc_18001807F
0x18001802a  mov     r15d, eax
0x18001802d  bts     r15d, 1Ch
0x180018032  mov     [rsp+278h+var_1D8], r15d
0x18001803a  mov     rdi, [rsp+278h+var_1A8]
0x180018042  mov     rsi, [rsp+278h+var_198]
0x18001804a  mov     rax, [rsp+278h+var_188]
0x180018052  mov     [rsp+278h+var_208], rax
0x180018057  mov     r14, [rsp+278h+var_180]
0x18001805f  mov     r12, [rsp+278h+var_178]
0x180018067  mov     rax, [rsp+278h+var_170]
0x18001806f  mov     [rsp+278h+var_1C0], rax
0x180018077  mov     r13, [rsp+278h+var_168]
0x18001807f  mov     rcx, [r13+0]
0x180018083  mov     rax, [rcx]
0x180018086  mov     rdx, [rsp+278h+var_210]
0x18001808b  mov     rax, [rax+68h]
0x18001808f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018094  test    r15d, r15d
0x180018097  jz      loc_1800182D2
0x18001809d  or      dword ptr [rsi+0B0h], 4
0x1800180a4  mov     rcx, [rsi+20h]
0x1800180a8  mov     rax, [rcx]
0x1800180ab  mov     rdx, [rsp+278h+var_1C0]
0x1800180b3  mov     rdx, [rdx]
0x1800180b6  mov     rax, [rax+18h]
0x1800180ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180bf  mov     rcx, [rsi+20h]
0x1800180c3  mov     rax, [rcx]
  ... truncated ...
```
