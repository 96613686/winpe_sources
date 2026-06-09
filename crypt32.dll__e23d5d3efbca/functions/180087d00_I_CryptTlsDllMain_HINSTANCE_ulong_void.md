# I_CryptTlsDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x180087d00`
- end: `0x180087ee9`
- name: `?I_CryptTlsDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `489`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800944a0`

## callees

- `0x180028d60`
- `0x1800449d4`
- `0x180087d00`
- `0x180087ef0`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087d92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087ec8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087d92`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180087ec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087def`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087e59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087def`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087e59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087da5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087e76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087da5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087e76`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180087d7e`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180087d7e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180087d4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180087d4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180087de6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180087de6`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180087ed4`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180087ed4`
- `MSASN1!ASN1_CloseDecoder` at `0x180087e2b`
- `MSASN1!ASN1_CloseDecoder` at `0x180087e2b`
- `MSASN1!ASN1_CloseEncoder` at `0x180087e1c`
- `MSASN1!ASN1_CloseEncoder` at `0x180087e1c`

## pseudocode

```c
__int64 __fastcall I_CryptTlsDllMain(HINSTANCE a1, __int64 a2, void *a3)
{
  int v3; // r13d
  unsigned int v4; // esi
  _DWORD *Value; // rax
  _QWORD *v7; // rdi
  int v8; // ebp
  unsigned int v9; // r12d
  __int64 v10; // rbp
  _QWORD *v11; // r15
  int v12; // [rsp+68h] [rbp+10h]
  unsigned int v13; // [rsp+78h] [rbp+20h]

  v12 = a2;
  v3 = a2;
  v4 = 1;
  switch ( (_DWORD)a2 )
  {
    case 0:
      goto LABEL_5;
    case 1:
      if ( (unsigned int)Pki_InitializeCriticalSection(&stru_18015CD98, a2, a3) )
      {
        dwTlsIndex = TlsAlloc();
        if ( dwTlsIndex != -1 )
          return v4;
        DeleteCriticalSection(&stru_18015CD98);
      }
      return 0;
    case 3:
LABEL_5:
      Value = TlsGetValue(dwTlsIndex);
      v7 = Value;
      if ( Value )
      {
        v8 = *Value;
        v13 = *Value;
        EnterCriticalSection(&stru_18015CD98);
        v9 = 0;
        if ( v8 )
        {
          v10 = 0;
          do
          {
            v11 = *(_QWORD **)(v7[1] + 8 * v10);
            if ( v11 )
            {
              if ( *((_DWORD *)qword_18015D668 + 4 * v10) == 1 )
              {
                if ( *((_QWORD *)qword_18015D668 + 2 * v10 + 1) )
                {
                  LeaveCriticalSection(&stru_18015CD98);
                  (*((void (__fastcall **)(_QWORD *))qword_18015D668 + 2 * v10 + 1))(v11);
                  EnterCriticalSection(&stru_18015CD98);
                }
              }
              else if ( *((_DWORD *)qword_18015D668 + 4 * v10) == 3 )
              {
                if ( *v11 )
                  ASN1_CloseEncoder();
                if ( v11[1] )
                  ASN1_CloseDecoder();
                PkiDefaultCryptFree(v11);
                *(_QWORD *)(v7[1] + 8 * v10) = 0;
              }
            }
            ++v9;
            ++v10;
          }
          while ( v9 < v13 );
          v3 = v12;
        }
        FreeCryptTls(v7);
        TlsSetValue(dwTlsIndex, 0);
        LeaveCriticalSection(&stru_18015CD98);
      }
      if ( !v3 )
      {
        while ( qword_18015CD90 )
          FreeCryptTls(qword_18015CD90);
        if ( qword_18015D668 )
        {
          PkiDefaultCryptFree(qword_18015D668);
          qword_18015D668 = 0;
        }
        dword_18015D670 = 0;
        dword_18015D660 = 0;
        DeleteCriticalSection(&stru_18015CD98);
        TlsFree(dwTlsIndex);
        dwTlsIndex = -1;
      }
      break;
  }
  return v4;
}

```

## disassembly

```asm
0x180087d00  mov     [rsp+arg_0], rbx
0x180087d05  mov     [rsp+arg_8], edx
0x180087d09  push    rbp
0x180087d0a  push    rsi
0x180087d0b  push    rdi
0x180087d0c  push    r12
0x180087d0e  push    r13
0x180087d10  push    r14
0x180087d12  push    r15
0x180087d14  sub     rsp, 20h
0x180087d18  mov     r13d, edx
0x180087d1b  mov     eax, edx
0x180087d1d  mov     esi, 1
0x180087d22  test    edx, edx
0x180087d24  jz      short loc_180087D46
0x180087d26  sub     eax, esi
0x180087d28  jz      short loc_180087D6B
0x180087d2a  cmp     eax, 2
0x180087d2d  jz      short loc_180087D46
0x180087d2f  mov     rbx, [rsp+58h+arg_0]
0x180087d34  mov     eax, esi
0x180087d36  add     rsp, 20h
0x180087d3a  pop     r15
0x180087d3c  pop     r14
0x180087d3e  pop     r13
0x180087d40  pop     r12
0x180087d42  pop     rdi
0x180087d43  pop     rsi
0x180087d44  pop     rbp
0x180087d45  retn
0x180087d46  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180087d4c  call    cs:__imp_TlsGetValue
0x180087d52  lea     rbx, stru_18015CD98
0x180087d59  mov     rdi, rax
0x180087d5c  test    rax, rax
0x180087d5f  jnz     short loc_180087D9C
0x180087d61  test    r13d, r13d
0x180087d64  jnz     short loc_180087D2F
0x180087d66  jmp     loc_180087E89
0x180087d6b  lea     rbx, stru_18015CD98
0x180087d72  mov     rcx, rbx
0x180087d75  call    Pki_InitializeCriticalSection
0x180087d7a  test    eax, eax
0x180087d7c  jz      short loc_180087D98
0x180087d7e  call    cs:__imp_TlsAlloc
0x180087d84  mov     cs:dwTlsIndex, eax
0x180087d8a  cmp     eax, 0FFFFFFFFh
0x180087d8d  jnz     short loc_180087D2F
0x180087d8f  mov     rcx, rbx; lpCriticalSection
0x180087d92  call    cs:__imp_DeleteCriticalSection
0x180087d98  xor     esi, esi
0x180087d9a  jmp     short loc_180087D2F
0x180087d9c  mov     ebp, [rax]
0x180087d9e  mov     rcx, rbx; lpCriticalSection
0x180087da1  mov     [rsp+58h+arg_18], ebp
0x180087da5  call    cs:__imp_EnterCriticalSection
0x180087dab  xor     r12d, r12d
0x180087dae  test    ebp, ebp
0x180087db0  jz      short loc_180087DD6
0x180087db2  mov     r13d, [rsp+58h+arg_18]
0x180087db7  xor     ebp, ebp
0x180087db9  mov     rax, [rdi+8]
0x180087dbd  mov     r15, [rax+rbp*8]
0x180087dc1  test    r15, r15
0x180087dc4  jnz     short loc_180087DFA
0x180087dc6  add     r12d, esi
0x180087dc9  add     rbp, rsi
0x180087dcc  cmp     r12d, r13d
0x180087dcf  jb      short loc_180087DB9
0x180087dd1  mov     r13d, [rsp+58h+arg_8]
0x180087dd6  mov     rcx, rdi; hMem
0x180087dd9  call    FreeCryptTls
0x180087dde  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180087de4  xor     edx, edx; lpTlsValue
0x180087de6  call    cs:__imp_TlsSetValue
0x180087dec  mov     rcx, rbx; lpCriticalSection
0x180087def  call    cs:__imp_LeaveCriticalSection
0x180087df5  jmp     loc_180087D61
0x180087dfa  mov     rdx, cs:qword_18015D668
0x180087e01  mov     r14, rbp
0x180087e04  add     r14, r14
0x180087e07  mov     ecx, [rdx+r14*8]
0x180087e0b  sub     ecx, esi
0x180087e0d  jz      short loc_180087E4A
0x180087e0f  cmp     ecx, 2
0x180087e12  jnz     short loc_180087DC6
0x180087e14  mov     rcx, [r15]
0x180087e17  test    rcx, rcx
0x180087e1a  jz      short loc_180087E22
0x180087e1c  call    cs:__imp_ASN1_CloseEncoder
0x180087e22  mov     rcx, [r15+8]
0x180087e26  test    rcx, rcx
0x180087e29  jz      short loc_180087E31
0x180087e2b  call    cs:__imp_ASN1_CloseDecoder
0x180087e31  mov     rcx, r15; hMem
0x180087e34  call    PkiDefaultCryptFree
0x180087e39  mov     rax, [rdi+8]
0x180087e3d  mov     qword ptr [rax+rbp*8], 0
0x180087e45  jmp     loc_180087DC6
0x180087e4a  cmp     qword ptr [rdx+r14*8+8], 0
0x180087e50  jz      loc_180087DC6
0x180087e56  mov     rcx, rbx; lpCriticalSection
0x180087e59  call    cs:__imp_LeaveCriticalSection
0x180087e5f  mov     rax, cs:qword_18015D668
0x180087e66  mov     rcx, r15
0x180087e69  mov     rax, [rax+r14*8+8]
0x180087e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087e73  mov     rcx, rbx; lpCriticalSection
0x180087e76  call    cs:__imp_EnterCriticalSection
0x180087e7c  jmp     loc_180087DC6
0x180087e81  mov     rcx, rax; hMem
0x180087e84  call    FreeCryptTls
0x180087e89  mov     rax, cs:qword_18015CD90
0x180087e90  test    rax, rax
0x180087e93  jnz     short loc_180087E81
0x180087e95  mov     rcx, cs:qword_18015D668; hMem
0x180087e9c  test    rcx, rcx
0x180087e9f  jz      short loc_180087EB1
0x180087ea1  call    PkiDefaultCryptFree
0x180087ea6  mov     cs:qword_18015D668, 0
0x180087eb1  mov     rcx, rbx; lpCriticalSection
0x180087eb4  mov     cs:dword_18015D670, 0
0x180087ebe  mov     cs:dword_18015D660, 0
0x180087ec8  call    cs:__imp_DeleteCriticalSection
0x180087ece  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180087ed4  call    cs:__imp_TlsFree
0x180087eda  mov     cs:dwTlsIndex, 0FFFFFFFFh
0x180087ee4  jmp     loc_180087D2F
```
