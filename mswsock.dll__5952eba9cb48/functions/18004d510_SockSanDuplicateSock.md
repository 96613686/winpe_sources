# SockSanDuplicateSock

- ea: `0x18004d510`
- end: `0x18004d83b`
- name: `SockSanDuplicateSock`
- size: `811`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18004abd0`
- `0x18004d450`

## callees

- `0x18002535c`
- `0x180038104`
- `0x180038118`
- `0x18003ad7c`
- `0x18003ae8c`
- `0x18003dae8`
- `0x18003dbe4`
- `0x18004bfb8`
- `0x18004d510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d69d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d69d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d5cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d5f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d7a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d5cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d5f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d7a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d595`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d595`

## pseudocode

```c
void __fastcall SockSanDuplicateSock(__int64 *a1, __int64 a2, int a3)
{
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // eax
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // r8
  char v14; // r14
  char v15; // al
  BOOL v16; // esi
  int v17; // eax
  int v18; // [rsp+28h] [rbp-50h]
  __int64 v19; // [rsp+50h] [rbp-28h] BYREF
  int v20; // [rsp+58h] [rbp-20h]
  __int128 v21; // [rsp+60h] [rbp-18h] BYREF

  v20 = 0;
  v19 = 0;
  v21 = 0;
  if ( SBYTE2(xmmword_180063D60) < 0 )
  {
    v18 = a3;
    WPP_SF_qqd(1047, 42, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, *(_QWORD *)(*a1 + 8), a1);
  }
  a1[23] = a2;
  *((_DWORD *)a1 + 48) = a3;
  a1[25] = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
  if ( *((_DWORD *)a1 + 44) )
  {
    if ( SBYTE2(xmmword_180063D60) < 0 )
      WPP_SF_(1047, 43, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids);
    *((_BYTE *)a1 + 208) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
    return;
  }
  if ( a1[13] == -1 && !*((_DWORD *)a1 + 38) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
    if ( *((_DWORD *)a1 + 42) == 2 )
      CloseSanHandle(a1);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_(1025, 44, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids);
    v7 = *a1;
    v8 = a1[27] + 24;
    LODWORD(v19) = 0;
    v9 = AfdTransferContext(v6, *(_QWORD *)(v7 + 8), v8, a2, (__int64)&v21, v18, (__int64)&v19, 0, -1073741504);
    if ( v9 < 0 && (xmmword_180063D60 & 2) != 0 )
    {
      v10 = 45;
LABEL_16:
      WPP_SF_d(1025, v10, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, (unsigned int)v9);
      return;
    }
    return;
  }
  if ( a3 != GetCurrentProcessId() )
  {
    _InterlockedIncrement((volatile signed __int32 *)a1[1]);
    *((_BYTE *)a1 + 801) &= ~1u;
    *((_DWORD *)a1 + 44) = 1;
    if ( (__int64 *)a1[50] != a1 + 50 || (v14 = 1, (__int64 *)a1[40] != a1 + 40) )
      v14 = 0;
    v16 = 1;
    if ( !*((_DWORD *)a1 + 34) )
    {
      v15 = *((_BYTE *)a1 + 800);
      if ( (v15 & 4) == 0 && ((v15 & 2) == 0 || !*((_DWORD *)a1 + 201)) )
        v16 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
    if ( v14 )
    {
      if ( v16 )
      {
        v17 = 0;
      }
      else
      {
        if ( SBYTE2(xmmword_180063D60) < 0 )
          WPP_SF_(1047, 48, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids);
        v17 = SendControlMessage(a1, 0, 0);
      }
      _InterlockedIncrement(&SockSanSocksDoingDup);
      if ( v17 )
      {
LABEL_43:
        ResumeSockDuplication(a1);
        return;
      }
    }
    else if ( SBYTE2(xmmword_180063D60) < 0 )
    {
      WPP_SF_(1047, 49, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids);
    }
    if ( !v16 )
      return;
    goto LABEL_43;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
  if ( SBYTE2(xmmword_180063D60) < 0 )
    WPP_SF_q(1047, 46, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, *(_QWORD *)(*a1 + 8));
  v12 = *a1;
  v13 = a1[27];
  BYTE10(v21) |= 2u;
  *(_QWORD *)&v21 = a1;
  LODWORD(v19) = 0;
  v9 = AfdTransferContext(v11, *(_QWORD *)(v12 + 8), (int)v13 + 24, a2, (__int64)&v21, v18, (__int64)&v19, 0, 0);
  if ( v9 < 0 && (xmmword_180063D60 & 2) != 0 )
  {
    v10 = 47;
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18004d510  push    rbp
0x18004d512  push    rbx
0x18004d513  push    rsi
0x18004d514  push    rdi
0x18004d515  push    r12
0x18004d517  push    r13
0x18004d519  push    r14
0x18004d51b  push    r15
0x18004d51d  mov     rbp, rsp
0x18004d520  sub     rsp, 78h
0x18004d524  xor     eax, eax
0x18004d526  xorps   xmm0, xmm0
0x18004d529  mov     [rbp+var_24], rax
0x18004d52d  mov     esi, r8d
0x18004d530  mov     [rbp-28h], rax
0x18004d534  mov     r14, rdx
0x18004d537  mov     rbx, rcx
0x18004d53a  movups  [rbp+var_18], xmm0
0x18004d53e  xor     r15d, r15d
0x18004d541  lea     r12, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004d548  cmp     byte ptr cs:xmmword_180063D60+2, r15b
0x18004d54f  mov     r13d, 417h
0x18004d555  jge     short loc_18004D576
0x18004d557  mov     r9, [rcx]
0x18004d55a  lea     edx, [rax+2Ah]
0x18004d55d  mov     dword ptr [rsp+78h+var_50], r8d
0x18004d562  mov     ecx, r13d
0x18004d565  mov     r8, r12
0x18004d568  mov     [rsp+78h+var_58], rbx
0x18004d56d  mov     r9, [r9+8]
0x18004d571  call    WPP_SF_qqd
0x18004d576  lea     rdi, [rbx+30h]
0x18004d57a  mov     [rbx+0B8h], r14
0x18004d581  mov     rcx, rdi; lpCriticalSection
0x18004d584  mov     [rbx+0C0h], esi
0x18004d58a  mov     qword ptr [rbx+0C8h], 0FFFFFFFFFFFFFFFFh
0x18004d595  call    cs:__imp_EnterCriticalSection
0x18004d59c  nop     dword ptr [rax+rax+00h]
0x18004d5a1  cmp     [rbx+0B0h], r15d
0x18004d5a8  jz      short loc_18004D5DE
0x18004d5aa  cmp     byte ptr cs:xmmword_180063D60+2, r15b
0x18004d5b1  jge     short loc_18004D5C3
0x18004d5b3  mov     edx, 2Bh ; '+'
0x18004d5b8  mov     ecx, r13d
0x18004d5bb  mov     r8, r12
0x18004d5be  call    WPP_SF_
0x18004d5c3  mov     rcx, rdi; lpCriticalSection
0x18004d5c6  mov     byte ptr [rbx+0D0h], 1
0x18004d5cd  call    cs:__imp_LeaveCriticalSection
0x18004d5d4  nop     dword ptr [rax+rax+00h]
0x18004d5d9  jmp     loc_18004D829
0x18004d5de  cmp     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x18004d5e3  jnz     loc_18004D69D
0x18004d5e9  cmp     [rbx+98h], r15d
0x18004d5f0  jnz     loc_18004D69D
0x18004d5f6  mov     rcx, rdi; lpCriticalSection
0x18004d5f9  call    cs:__imp_LeaveCriticalSection
0x18004d600  nop     dword ptr [rax+rax+00h]
0x18004d605  cmp     dword ptr [rbx+0A8h], 2
0x18004d60c  jnz     short loc_18004D616
0x18004d60e  mov     rcx, rbx
0x18004d611  call    CloseSanHandle
0x18004d616  test    byte ptr cs:xmmword_180063D60, 2
0x18004d61d  jz      short loc_18004D631
0x18004d61f  mov     edx, 2Ch ; ','
0x18004d624  mov     ecx, 401h
0x18004d629  mov     r8, r12
0x18004d62c  call    WPP_SF_
0x18004d631  mov     rdx, [rbx]
0x18004d634  lea     rax, [rbp+var_28]
0x18004d638  mov     r8, [rbx+0D8h]
0x18004d63f  mov     r9, r14
0x18004d642  mov     [rsp+78h+var_38], 0C0000140h
0x18004d64a  add     r8, 18h
0x18004d64e  mov     [rsp+78h+var_40], r15d
0x18004d653  mov     [rsp+78h+var_48], rax
0x18004d658  lea     rax, [rbp+var_18]
0x18004d65c  mov     [rbp+var_28], r15d
0x18004d660  mov     rdx, [rdx+8]
0x18004d664  mov     [rsp+78h+var_58], rax
0x18004d669  call    AfdTransferContext
0x18004d66e  test    eax, eax
0x18004d670  jns     loc_18004D829
0x18004d676  test    byte ptr cs:xmmword_180063D60, 2
0x18004d67d  jz      loc_18004D829
0x18004d683  mov     edx, 2Dh ; '-'
0x18004d688  mov     ecx, 401h
0x18004d68d  mov     r9d, eax
0x18004d690  mov     r8, r12
0x18004d693  call    WPP_SF_d
0x18004d698  jmp     loc_18004D829
0x18004d69d  call    cs:__imp_GetCurrentProcessId
0x18004d6a4  nop     dword ptr [rax+rax+00h]
0x18004d6a9  cmp     esi, eax
0x18004d6ab  jnz     loc_18004D741
0x18004d6b1  mov     rcx, rdi; lpCriticalSection
0x18004d6b4  call    cs:__imp_LeaveCriticalSection
0x18004d6bb  nop     dword ptr [rax+rax+00h]
0x18004d6c0  cmp     byte ptr cs:xmmword_180063D60+2, r15b
0x18004d6c7  jge     short loc_18004D6E0
0x18004d6c9  mov     r9, [rbx]
0x18004d6cc  mov     edx, 2Eh ; '.'
0x18004d6d1  mov     ecx, r13d
0x18004d6d4  mov     r8, r12
0x18004d6d7  mov     r9, [r9+8]
0x18004d6db  call    WPP_SF_q
0x18004d6e0  mov     rdx, [rbx]
0x18004d6e3  lea     rax, [rbp+var_28]
0x18004d6e7  mov     r8, [rbx+0D8h]
0x18004d6ee  mov     r9, r14
0x18004d6f1  or      byte ptr [rbp+var_18+0Ah], 2
0x18004d6f5  add     r8, 18h
0x18004d6f9  mov     [rsp+78h+var_38], r15d
0x18004d6fe  mov     [rsp+78h+var_40], r15d
0x18004d703  mov     [rsp+78h+var_48], rax
0x18004d708  lea     rax, [rbp+var_18]
0x18004d70c  mov     qword ptr [rbp+var_18], rbx
0x18004d710  mov     [rbp+var_28], r15d
0x18004d714  mov     rdx, [rdx+8]
0x18004d718  mov     [rsp+78h+var_58], rax
0x18004d71d  call    AfdTransferContext
0x18004d722  test    eax, eax
0x18004d724  jns     loc_18004D829
0x18004d72a  test    byte ptr cs:xmmword_180063D60, 2
0x18004d731  jz      loc_18004D829
0x18004d737  mov     edx, 2Fh ; '/'
0x18004d73c  jmp     loc_18004D688
0x18004d741  mov     rax, [rbx+8]
0x18004d745  lock inc dword ptr [rax]
0x18004d748  and     byte ptr [rbx+321h], 0FEh
0x18004d74f  lea     rax, [rbx+190h]
0x18004d756  mov     dword ptr [rbx+0B0h], 1
0x18004d760  cmp     [rax], rax
0x18004d763  jnz     short loc_18004D774
0x18004d765  lea     rax, [rbx+140h]
0x18004d76c  mov     r14b, 1
0x18004d76f  cmp     [rax], rax
0x18004d772  jz      short loc_18004D777
0x18004d774  mov     r14b, r15b
0x18004d777  cmp     [rbx+88h], r15d
0x18004d77e  jnz     short loc_18004D79C
0x18004d780  mov     al, [rbx+320h]
0x18004d786  test    al, 4
0x18004d788  jnz     short loc_18004D79C
0x18004d78a  test    al, 2
0x18004d78c  jz      short loc_18004D797
0x18004d78e  cmp     [rbx+324h], r15d
0x18004d795  jnz     short loc_18004D79C
0x18004d797  mov     esi, r15d
0x18004d79a  jmp     short loc_18004D7A1
0x18004d79c  mov     esi, 1
0x18004d7a1  mov     rcx, rdi; lpCriticalSection
0x18004d7a4  call    cs:__imp_LeaveCriticalSection
0x18004d7ab  nop     dword ptr [rax+rax+00h]
0x18004d7b0  test    r14b, r14b
0x18004d7b3  jz      short loc_18004D7F1
0x18004d7b5  test    esi, esi
0x18004d7b7  jnz     short loc_18004D7EC
0x18004d7b9  cmp     byte ptr cs:xmmword_180063D60+2, r15b
0x18004d7c0  jge     short loc_18004D7D0
0x18004d7c2  lea     edx, [rsi+30h]
0x18004d7c5  mov     ecx, r13d
0x18004d7c8  mov     r8, r12
0x18004d7cb  call    WPP_SF_
0x18004d7d0  mov     [rsp+78h+var_50], r15
0x18004d7d5  xor     r9d, r9d
0x18004d7d8  xor     r8d, r8d
0x18004d7db  mov     [rsp+78h+var_58], r15
0x18004d7e0  mov     dl, 0Fh
0x18004d7e2  mov     rcx, rbx
0x18004d7e5  call    SendControlMessage
0x18004d7ea  jmp     short loc_18004D80F
0x18004d7ec  test    r14b, r14b
0x18004d7ef  jnz     short loc_18004D80C
0x18004d7f1  cmp     byte ptr cs:xmmword_180063D60+2, r15b
0x18004d7f8  jge     short loc_18004D81D
0x18004d7fa  mov     edx, 31h ; '1'
0x18004d7ff  mov     ecx, r13d
0x18004d802  mov     r8, r12
0x18004d805  call    WPP_SF_
0x18004d80a  jmp     short loc_18004D81D
0x18004d80c  mov     eax, r15d
0x18004d80f  lea     rcx, SockSanSocksDoingDup
0x18004d816  lock inc dword ptr [rcx]
0x18004d819  test    eax, eax
0x18004d81b  jnz     short loc_18004D821
0x18004d81d  test    esi, esi
0x18004d81f  jz      short loc_18004D829
0x18004d821  mov     rcx, rbx
0x18004d824  call    ResumeSockDuplication
0x18004d829  add     rsp, 78h
0x18004d82d  pop     r15
0x18004d82f  pop     r14
0x18004d831  pop     r13
0x18004d833  pop     r12
0x18004d835  pop     rdi
0x18004d836  pop     rsi
0x18004d837  pop     rbx
0x18004d838  pop     rbp
0x18004d839  retn
```
