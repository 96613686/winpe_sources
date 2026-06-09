# PatchVTableEntriesForDLLAttach(PEDecoder *)

- ea: `0x18002f4d4`
- end: `0x18002f7d6`
- name: `?PatchVTableEntriesForDLLAttach@@YAHPEAVPEDecoder@@@Z`
- size: `770`
- prototype: `__int64 __fastcall(struct PEDecoder *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x18002efb4`

## callees

- `0x180004170`
- `0x1800060f0`
- `0x180029a34`
- `0x18002f454`
- `0x18002f498`
- `0x18002f4d4`
- `0x1800393f0`
- `0x18003e0e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002f624`
- `KERNEL32!EnterCriticalSection` at `0x18002f624`
- `KERNEL32!LeaveCriticalSection` at `0x18002f643`
- `KERNEL32!LeaveCriticalSection` at `0x18002f643`
- `KERNEL32!GetLastError` at `0x18002f5aa`
- `KERNEL32!GetLastError` at `0x18002f5aa`
- `KERNEL32!VirtualProtect` at `0x18002f6b4`
- `KERNEL32!VirtualProtect` at `0x18002f7a1`
- `KERNEL32!VirtualProtect` at `0x18002f6b4`
- `KERNEL32!VirtualProtect` at `0x18002f7a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PatchVTableEntriesForDLLAttach(struct PEDecoder *this)
{
  struct IMAGE_COR20_HEADER *CorHeader; // rax
  DWORD v3; // edi
  __int64 RvaData; // rsi
  DWORD v5; // r12d
  unsigned int v6; // eax
  DWORD i; // r8d
  __int64 v8; // r15
  void *ProcessExecutableHeap; // rcx
  __int64 v10; // rbx
  char *v11; // rax
  char *v12; // r13
  int v13; // r10d
  DWORD v14; // edi
  char *v15; // r11
  int v16; // r8d
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rcx
  int v21; // eax
  DWORD v23[4]; // [rsp+20h] [rbp-50h] BYREF
  __int128 v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+40h] [rbp-30h] BYREF
  char v26; // [rsp+48h] [rbp-28h]
  __int64 v27; // [rsp+50h] [rbp-20h] BYREF
  char v28; // [rsp+58h] [rbp-18h]
  int v29; // [rsp+59h] [rbp-17h]
  __int16 v30; // [rsp+5Dh] [rbp-13h]
  char v31; // [rsp+5Fh] [rbp-11h]
  char v32[16]; // [rsp+60h] [rbp-10h] BYREF
  DWORD LastError; // [rsp+B8h] [rbp+48h] BYREF
  int v34; // [rsp+BCh] [rbp+4Ch]
  DWORD flOldProtect; // [rsp+C0h] [rbp+50h] BYREF
  DWORD v36; // [rsp+C8h] [rbp+58h]

  if ( (PEDecoder::GetCorHeader(this)->Flags & 1) == 0 )
  {
    CorHeader = PEDecoder::GetCorHeader(this);
    v36 = CorHeader->VTableFixups.Size >> 3;
    v3 = v36;
    RvaData = PEDecoder::GetRvaData(this, CorHeader->VTableFixups.VirtualAddress);
    v5 = 0;
    if ( v3 )
    {
      v6 = 0;
      for ( i = 0; i < v3; ++i )
        v6 += *(unsigned __int16 *)(RvaData + 8LL * i + 4);
      v27 = 24;
      v28 = 0;
      v25 = 48;
      v26 = 0;
      v8 = v6;
      *(_QWORD *)&v24 = v6;
      BYTE8(v24) = 0;
      v24 = *(_OWORD *)ClrSafeInt<unsigned __int64>::operator*(&v25, v32, &v24);
      ClrSafeInt<unsigned __int64>::operator+(&v27, &v25, &v24);
      if ( v26 )
        return 0;
      LastError = GetLastError();
      v34 = 2;
      ProcessExecutableHeap = ClrGetProcessExecutableHeap();
      if ( ProcessExecutableHeap )
      {
        *(_QWORD *)&v24 = v25;
        BYTE8(v24) = 0;
        *(_DWORD *)((char *)&v24 + 9) = v29;
        *(_WORD *)((char *)&v24 + 13) = v30;
        HIBYTE(v24) = v31;
        v10 = ClrHeapAlloc(ProcessExecutableHeap, 0, &v24);
      }
      else
      {
        v10 = 0;
      }
      SaveLastErrorHolder::~SaveLastErrorHolder((SaveLastErrorHolder *)&LastError);
      if ( !v10 )
        return 0;
      *(_QWORD *)v10 = *(_QWORD *)this;
      *(_QWORD *)(v10 + 8) = v8;
      *(_QWORD *)(v10 + 16) = 0;
      EnterCriticalSection(&g_chunkLock);
      *(_QWORD *)(v10 + 16) = g_pVTableBootstrapThunkChunkList;
      g_pVTableBootstrapThunkChunkList = (struct VTableBootstrapThunkChunk *)v10;
      LeaveCriticalSection(&g_chunkLock);
      LastError = 0;
      while ( v5 < v3 )
      {
        if ( ((*(_WORD *)(RvaData + 8LL * v5 + 6) - 2) & 0xFFF3) == 0 && *(_WORD *)(RvaData + 8LL * v5 + 6) != 14 )
        {
          v11 = (char *)PEDecoder::GetRvaData(this, *(unsigned int *)(RvaData + 8LL * v5));
          v12 = v11;
          if ( !v11 )
            return 0;
          flOldProtect = 0;
          if ( !VirtualProtect(v11, 8LL * *(unsigned __int16 *)(RvaData + 8LL * v5 + 4), 4u, &flOldProtect) )
            return 0;
          v13 = 0;
          if ( *(_WORD *)(RvaData + 8LL * v5 + 4) )
          {
            v14 = LastError;
            do
            {
              v15 = &v12[8 * v13];
              v16 = *(_DWORD *)v15;
              v17 = v14++;
              v18 = 48 * v17;
              v19 = v10 + 48 * v17 + 24;
              v20 = *(_QWORD *)this;
              *(_WORD *)v19 = (_WORD)VTableBootstrapThunkCode::s_mov_r10;
              *(_QWORD *)(v19 + 2) = v19;
              *(_WORD *)(v19 + 10) = (_WORD)VTableBootstrapThunkCode::s_mov_r11;
              *(_QWORD *)(v19 + 12) = VTableBootstrapThunkInitHelperStub;
              *(_WORD *)(v18 + v10 + 44) = (_WORD)VTableBootstrapThunkCode::s_jmp_r11;
              *(_BYTE *)(v18 + v10 + 46) = byte_18005FF8A;
              *(_DWORD *)(v19 + 24) = v16;
              *(_QWORD *)(v19 + 32) = v20;
              *(_QWORD *)(v19 + 40) = v15;
              *(_DWORD *)(v19 + 28) = 0;
              if ( (v16 & 0xFF000000) == 0x6000000 )
                *(_DWORD *)(v19 + 28) = 1;
              *(_QWORD *)v15 = v19;
              ++v13;
              v21 = *(unsigned __int16 *)(RvaData + 8LL * v5 + 4);
            }
            while ( v13 < v21 );
            LastError = v14;
            v3 = v36;
          }
          else
          {
            LOWORD(v21) = 0;
          }
          v23[0] = 0;
          VirtualProtect(v12, 8LL * (unsigned __int16)v21, flOldProtect, v23);
        }
        ++v5;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18002f4d4  mov     [rsp-38h+arg_0], rbx
0x18002f4d9  push    rbp
0x18002f4da  push    rsi
0x18002f4db  push    rdi
0x18002f4dc  push    r12
0x18002f4de  push    r13
0x18002f4e0  push    r14
0x18002f4e2  push    r15
0x18002f4e4  mov     rbp, rsp
0x18002f4e7  sub     rsp, 70h
0x18002f4eb  mov     r14, rcx
0x18002f4ee  call    ?GetCorHeader@PEDecoder@@QEBAPEAUIMAGE_COR20_HEADER@@XZ; PEDecoder::GetCorHeader(void)
0x18002f4f3  test    byte ptr [rax+10h], 1
0x18002f4f7  jnz     loc_18002F7B9
0x18002f4fd  mov     rcx, r14; this
0x18002f500  call    ?GetCorHeader@PEDecoder@@QEBAPEAUIMAGE_COR20_HEADER@@XZ; PEDecoder::GetCorHeader(void)
0x18002f505  mov     edi, [rax+34h]
0x18002f508  shr     edi, 3
0x18002f50b  mov     [rbp+arg_18], edi
0x18002f50e  mov     edx, [rax+30h]
0x18002f511  mov     rcx, r14
0x18002f514  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18002f519  mov     rsi, rax
0x18002f51c  xor     r12d, r12d
0x18002f51f  test    edi, edi
0x18002f521  jz      loc_18002F7B9
0x18002f527  mov     eax, r12d
0x18002f52a  mov     r8d, r12d
0x18002f52d  mov     ecx, r8d
0x18002f530  movzx   edx, word ptr [rsi+rcx*8+4]
0x18002f535  add     eax, edx
0x18002f537  inc     r8d
0x18002f53a  cmp     r8d, edi
0x18002f53d  jb      short loc_18002F52D
0x18002f53f  mov     [rbp+var_20], 18h
0x18002f547  mov     [rbp+var_18], r12b
0x18002f54b  mov     [rbp+var_30], 30h ; '0'
0x18002f553  mov     [rbp+var_28], r12b
0x18002f557  mov     r15d, eax
0x18002f55a  mov     qword ptr [rbp+var_40], r15
0x18002f55e  mov     byte ptr [rbp+var_40+8], r12b
0x18002f562  mov     eax, dword ptr [rbp+var_40+9]
0x18002f565  mov     dword ptr [rbp+var_40+9], eax
0x18002f568  movzx   eax, word ptr [rbp+var_40+0Dh]
0x18002f56c  mov     word ptr [rbp+var_40+0Dh], ax
0x18002f570  mov     al, byte ptr [rbp+var_40+0Fh]
0x18002f573  mov     byte ptr [rbp+var_40+0Fh], al
0x18002f576  lea     r8, [rbp+var_40]
0x18002f57a  lea     rdx, [rbp+var_10]
0x18002f57e  lea     rcx, [rbp+var_30]
0x18002f582  call    ??D?$ClrSafeInt@_K@@QEBA?AV0@V0@@Z; ClrSafeInt<unsigned __int64>::operator*(ClrSafeInt<unsigned __int64>)
0x18002f587  movups  xmm0, xmmword ptr [rax]
0x18002f58a  movdqu  [rbp+var_40], xmm0
0x18002f58f  lea     r8, [rbp+var_40]
0x18002f593  lea     rdx, [rbp+var_30]
0x18002f597  lea     rcx, [rbp+var_20]
0x18002f59b  call    ??H?$ClrSafeInt@_K@@QEBA?AV0@V0@@Z; ClrSafeInt<unsigned __int64>::operator+(ClrSafeInt<unsigned __int64>)
0x18002f5a0  cmp     [rbp+var_28], r12b
0x18002f5a4  jnz     loc_18002F7B5
0x18002f5aa  call    cs:__imp_GetLastError
0x18002f5b0  mov     [rbp+arg_8], eax
0x18002f5b3  mov     r13d, 2
0x18002f5b9  mov     [rbp+arg_C], r13d
0x18002f5bd  call    ?ClrGetProcessExecutableHeap@@YAPEAXXZ; ClrGetProcessExecutableHeap(void)
0x18002f5c2  mov     rcx, rax
0x18002f5c5  test    rax, rax
0x18002f5c8  jnz     short loc_18002F5CF
0x18002f5ca  mov     rbx, r12
0x18002f5cd  jmp     short loc_18002F5FD
0x18002f5cf  mov     rax, [rbp+var_30]
0x18002f5d3  mov     qword ptr [rbp+var_40], rax
0x18002f5d7  mov     byte ptr [rbp+var_40+8], r12b
0x18002f5db  mov     eax, [rbp+var_17]
0x18002f5de  mov     dword ptr [rbp+var_40+9], eax
0x18002f5e1  movzx   eax, [rbp+var_13]
0x18002f5e5  mov     word ptr [rbp+var_40+0Dh], ax
0x18002f5e9  mov     al, [rbp+var_11]
0x18002f5ec  mov     byte ptr [rbp+var_40+0Fh], al
0x18002f5ef  lea     r8, [rbp+var_40]
0x18002f5f3  xor     edx, edx
0x18002f5f5  call    ?ClrHeapAlloc@@YAPEAXPEAXKV?$ClrSafeInt@_K@@@Z; ClrHeapAlloc(void *,ulong,ClrSafeInt<unsigned __int64>)
0x18002f5fa  mov     rbx, rax
0x18002f5fd  lea     rcx, [rbp+arg_8]; this
0x18002f601  call    ??1SaveLastErrorHolder@@QEAA@XZ; SaveLastErrorHolder::~SaveLastErrorHolder(void)
0x18002f606  test    rbx, rbx
0x18002f609  jz      loc_18002F7B5
0x18002f60f  mov     rcx, [r14]
0x18002f612  mov     [rbx], rcx
0x18002f615  mov     [rbx+8], r15
0x18002f619  mov     [rbx+10h], r12
0x18002f61d  lea     rcx, ?g_chunkLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f624  call    cs:__imp_EnterCriticalSection
0x18002f62a  mov     rax, cs:?g_pVTableBootstrapThunkChunkList@@3PEAVVTableBootstrapThunkChunk@@EA; VTableBootstrapThunkChunk * g_pVTableBootstrapThunkChunkList
0x18002f631  mov     [rbx+10h], rax
0x18002f635  mov     cs:?g_pVTableBootstrapThunkChunkList@@3PEAVVTableBootstrapThunkChunk@@EA, rbx; VTableBootstrapThunkChunk * g_pVTableBootstrapThunkChunkList
0x18002f63c  lea     rcx, ?g_chunkLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f643  call    cs:__imp_LeaveCriticalSection
0x18002f649  mov     [rbp+arg_8], r12d
0x18002f64d  cmp     r12d, edi
0x18002f650  jnb     loc_18002F7B9
0x18002f656  mov     r15d, r12d
0x18002f659  movzx   eax, word ptr [rsi+r15*8+6]
0x18002f65f  sub     ax, r13w
0x18002f663  mov     ecx, 0FFF3h
0x18002f668  test    cx, ax
0x18002f66b  jnz     loc_18002F7AD
0x18002f671  cmp     word ptr [rsi+r15*8+6], 0Eh
0x18002f678  jz      loc_18002F7AD
0x18002f67e  mov     edx, [rsi+r15*8]
0x18002f682  mov     rcx, r14
0x18002f685  call    ?GetRvaData@PEDecoder@@QEBA_KKW4IsNullOK@@@Z; PEDecoder::GetRvaData(ulong,IsNullOK)
0x18002f68a  mov     r13, rax
0x18002f68d  test    rax, rax
0x18002f690  jz      loc_18002F7B5
0x18002f696  mov     [rbp+flOldProtect], 0
0x18002f69d  movzx   edx, word ptr [rsi+r15*8+4]
0x18002f6a3  shl     rdx, 3; dwSize
0x18002f6a7  lea     r9, [rbp+flOldProtect]; lpflOldProtect
0x18002f6ab  mov     r8d, 4; flNewProtect
0x18002f6b1  mov     rcx, rax; lpAddress
0x18002f6b4  call    cs:__imp_VirtualProtect
0x18002f6ba  test    eax, eax
0x18002f6bc  jz      loc_18002F7B5
0x18002f6c2  xor     r10d, r10d
0x18002f6c5  movzx   ecx, word ptr [rsi+r15*8+4]
0x18002f6cb  xor     eax, eax
0x18002f6cd  cmp     ax, cx
0x18002f6d0  jnb     loc_18002F785
0x18002f6d6  mov     edi, [rbp+arg_8]
0x18002f6d9  movsxd  rax, r10d
0x18002f6dc  lea     r11, ds:0[rax*8]
0x18002f6e4  add     r11, r13
0x18002f6e7  mov     r8d, [r11]
0x18002f6ea  mov     eax, edi
0x18002f6ec  inc     edi
0x18002f6ee  lea     rdx, [rax+rax*2]
0x18002f6f2  shl     rdx, 4
0x18002f6f6  lea     r9, [rdx+18h]
0x18002f6fa  add     r9, rbx
0x18002f6fd  mov     rcx, [r14]
0x18002f700  movzx   eax, cs:?s_mov_r10@VTableBootstrapThunkCode@@0PAEA; uchar near * VTableBootstrapThunkCode::s_mov_r10
0x18002f707  mov     [r9], ax
0x18002f70b  mov     [r9+2], r9
0x18002f70f  movzx   eax, cs:?s_mov_r11@VTableBootstrapThunkCode@@0PAEA; uchar near * VTableBootstrapThunkCode::s_mov_r11
0x18002f716  mov     [r9+0Ah], ax
0x18002f71b  lea     rax, VTableBootstrapThunkInitHelperStub
0x18002f722  mov     [r9+0Ch], rax
0x18002f726  movzx   eax, cs:?s_jmp_r11@VTableBootstrapThunkCode@@0PAEA; uchar near * VTableBootstrapThunkCode::s_jmp_r11
0x18002f72d  mov     [rdx+rbx+2Ch], ax
0x18002f732  mov     al, cs:byte_18005FF8A
0x18002f738  mov     [rdx+rbx+2Eh], al
0x18002f73c  mov     [r9+18h], r8d
0x18002f740  mov     [r9+20h], rcx
0x18002f744  mov     [r9+28h], r11
0x18002f748  mov     dword ptr [r9+1Ch], 0
0x18002f750  and     r8d, 0FF000000h
0x18002f757  cmp     r8d, 6000000h
0x18002f75e  jnz     short loc_18002F768
0x18002f760  mov     dword ptr [r9+1Ch], 1
0x18002f768  mov     [r11], r9
0x18002f76b  inc     r10d
0x18002f76e  movzx   eax, word ptr [rsi+r15*8+4]
0x18002f774  cmp     r10d, eax
0x18002f777  jl      loc_18002F6D9
0x18002f77d  mov     [rbp+arg_8], edi
0x18002f780  mov     edi, [rbp+arg_18]
0x18002f783  jmp     short loc_18002F788
0x18002f785  movzx   eax, cx
0x18002f788  mov     [rbp+var_50], 0
0x18002f78f  movzx   edx, ax
0x18002f792  shl     rdx, 3; dwSize
0x18002f796  lea     r9, [rbp+var_50]; lpflOldProtect
0x18002f79a  mov     r8d, [rbp+flOldProtect]; flNewProtect
0x18002f79e  mov     rcx, r13; lpAddress
0x18002f7a1  call    cs:__imp_VirtualProtect
0x18002f7a7  mov     r13d, 2
0x18002f7ad  inc     r12d
0x18002f7b0  jmp     loc_18002F64D
0x18002f7b5  xor     eax, eax
0x18002f7b7  jmp     short loc_18002F7BE
0x18002f7b9  mov     eax, 1
0x18002f7be  mov     rbx, [rsp+70h+arg_0]
0x18002f7c6  add     rsp, 70h
0x18002f7ca  pop     r15
0x18002f7cc  pop     r14
0x18002f7ce  pop     r13
0x18002f7d0  pop     r12
0x18002f7d2  pop     rdi
0x18002f7d3  pop     rsi
0x18002f7d4  pop     rbp
0x18002f7d5  retn
```
