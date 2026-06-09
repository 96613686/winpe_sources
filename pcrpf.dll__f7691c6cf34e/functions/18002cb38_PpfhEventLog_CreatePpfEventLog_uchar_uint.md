# PpfhEventLog::CreatePpfEventLog(uchar * *,uint *)

- ea: `0x18002cb38`
- end: `0x18002cfa0`
- name: `?CreatePpfEventLog@PpfhEventLog@@QEAAXPEAPEAEPEAI@Z`
- size: `1128`
- prototype: `void __fastcall(PpfhEventLog *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18004b710`

## callees

- `0x180027818`
- `0x1800278c4`
- `0x180027944`
- `0x1800290f4`
- `0x18002919c`
- `0x18002cb38`
- `0x180034f7c`
- `0x180034fd8`
- `0x180034ff8`
- `0x1800570b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ccf8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ccf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cce4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cedd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cc72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cce4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cedd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cef1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cc86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cef1`

## string_xrefs

- `0x18002cd74`: `PpfEvtLogWriteDigestTableEntry`
- `0x18002ce76`: `PpfEvtLogWriteDigestTableEntry`

## pseudocode

```c
void __fastcall PpfhEventLog::CreatePpfEventLog(PpfhEventLog *this, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned int v4; // r9d
  unsigned int v5; // esi
  __int64 v6; // rbx
  __int64 v7; // r12
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // r15
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // edx
  unsigned int v13; // ecx
  int v14; // eax
  int v15; // eax
  unsigned int v16; // r8d
  void *v17; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v19; // rsi
  __int64 v20; // r12
  unsigned int v21; // r13d
  unsigned __int16 *v22; // rbx
  unsigned __int16 *v23; // rdi
  int v24; // eax
  unsigned int v25; // r8d
  HANDLE v26; // rax
  int v27; // edx
  const char *v28; // r9
  char *v29; // r15
  unsigned __int16 *v30; // r14
  unsigned __int16 *v31; // rbx
  size_t v32; // r12
  unsigned __int16 v33; // bx
  int v34; // eax
  int v35; // edi
  unsigned int v36; // r8d
  __int64 v37; // rax
  unsigned int v38; // edx
  unsigned int v39; // ebx
  int v40; // eax
  unsigned int v41; // r8d
  HANDLE v42; // rax
  int Format; // [rsp+20h] [rbp-69h]
  int Formata; // [rsp+20h] [rbp-69h]
  size_t Size; // [rsp+28h] [rbp-61h]
  size_t v46; // [rsp+38h] [rbp-51h]
  unsigned __int16 *v47; // [rsp+50h] [rbp-39h]
  unsigned int v48; // [rsp+58h] [rbp-31h] BYREF
  int v49[2]; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int8 *v50; // [rsp+68h] [rbp-21h] BYREF
  void **v51; // [rsp+70h] [rbp-19h]
  void *v52; // [rsp+78h] [rbp-11h] BYREF
  char v53; // [rsp+80h] [rbp-9h]
  char *v54; // [rsp+88h] [rbp-1h]
  void *Src; // [rsp+90h] [rbp+7h]
  __int64 v56; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  unsigned int v58; // [rsp+F0h] [rbp+67h] BYREF
  unsigned __int8 **v59; // [rsp+F8h] [rbp+6Fh]
  unsigned int *v60; // [rsp+100h] [rbp+77h]
  unsigned int v61; // [rsp+108h] [rbp+7Fh]

  v60 = a3;
  v59 = a2;
  v4 = 0;
  v58 = 0;
  v5 = 0;
  v6 = *((_QWORD *)this + 1);
  v7 = *((_QWORD *)this + 2);
  if ( v6 != v7 )
  {
    do
    {
      v8 = *(unsigned __int16 **)(v6 + 8);
      v9 = *(unsigned __int16 **)(v6 + 16);
      while ( v8 != v9 )
      {
        v10 = PpfEvtLogAccumulateDigestTableSize(*v8, &v58);
        if ( v10 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x508, v11, (const char *)(unsigned int)v10, Format);
        v8 += 12;
      }
      v12 = v5;
      v13 = v5 + *(_DWORD *)(v6 + 40);
      v14 = -1;
      if ( v13 >= v5 )
        v14 = v5 + *(_DWORD *)(v6 + 40);
      v5 = v14;
      if ( v13 < v12 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x50A,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
          v13 < v12 ? (const char *)0x80070216LL : 0,
          Format);
      v6 += 56;
    }
    while ( v6 != v7 );
    v4 = v58;
  }
  v50 = 0;
  v48 = 0;
  *(_QWORD *)v49 = 0;
  v51 = (void **)&v50;
  v52 = 0;
  v53 = 1;
  v15 = PpfEvtLogAllocateAndInitializeHeader(
          *(unsigned __int16 *)this,
          *((_DWORD *)this + 1),
          -1227133513 * (unsigned int)((__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 3),
          v4,
          v5,
          0,
          (__int64)&v52,
          (__int64)&v48,
          (__int64)v49);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x513, v16, (const char *)(unsigned int)v15, Formata);
  if ( v53 )
  {
    v17 = *v51;
    *v51 = v52;
    if ( v17 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v17);
    }
  }
  v19 = *((_QWORD *)this + 1);
  v20 = *((_QWORD *)this + 2);
  v56 = v20;
  while ( v19 != v20 )
  {
    v54 = 0;
    v21 = 0;
    v58 = 0;
    v22 = *(unsigned __int16 **)(v19 + 8);
    v23 = *(unsigned __int16 **)(v19 + 16);
    if ( v22 != v23 )
    {
      do
      {
        v24 = PpfEvtLogAccumulateDigestTableSize(*v22, &v58);
        if ( v24 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x51C, v25, (const char *)(unsigned int)v24, Formata);
        v22 += 12;
      }
      while ( v22 != v23 );
      v21 = v58;
    }
    v26 = GetProcessHeap();
    v29 = (char *)HeapAlloc(v26, 0, v21);
    v54 = v29;
    if ( !v29 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x51F,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        v28);
    v30 = *(unsigned __int16 **)(v19 + 8);
    v31 = *(unsigned __int16 **)(v19 + 16);
    v47 = v31;
    if ( v30 != v31 )
    {
      v61 = 0;
      do
      {
        Src = (void *)*((_QWORD *)v30 + 1);
        LOWORD(v58) = 0;
        if ( Src )
        {
          v32 = v30[8];
          v33 = *v30;
          v34 = PpfEvtLogValidateDigestAlgIDAndGetSize(*v30, &v58);
          v35 = v34;
          if ( v34 >= 0 )
          {
            if ( (_WORD)v58 == (_WORD)v32 )
            {
              v37 = (unsigned int)(v32 + 2);
              v38 = v61;
              if ( (unsigned int)v37 + v61 < v61 )
              {
                v35 = -1073741675;
                PpfEvtLogTraceHelper(
                  (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
                  1308,
                  (int)"PpfEvtLogWriteDigestTableEntry",
                  1,
                  "Error: 0x%x",
                  149);
              }
              else if ( (unsigned int)v37 + v61 <= v21 )
              {
                if ( &v29[v37] < v29 )
                {
                  v35 = -1073741675;
                  PpfEvtLogTraceHelper(
                    (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
                    1320,
                    (int)"PpfEvtLogWriteDigestTableEntry",
                    1,
                    "Error: 0x%x",
                    149);
                }
                else
                {
                  v35 = 0;
                  *(_WORD *)&v29[v61] = v33;
                  v39 = v38 + 2;
                  memcpy_0(&v29[v38 + 2], Src, v32);
                  v61 = v39 + v32;
                }
              }
              else
              {
                v35 = -1073741811;
                PpfEvtLogTraceHelper(
                  (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
                  1311,
                  (int)"PpfEvtLogWriteDigestTableEntry",
                  1,
                  "Error: 0x%x",
                  13);
              }
            }
            else
            {
              v35 = -1073741811;
              PpfEvtLogTraceHelper(
                (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
                1293,
                (int)"PpfEvtLogWriteDigestTableEntry",
                1,
                "Error: 0x%x",
                13);
            }
          }
          else
          {
            PpfEvtLogTraceHelper(
              (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
              1289,
              (int)"PpfEvtLogWriteDigestTableEntry",
              1,
              "Error: 0x%x",
              v34);
          }
          v31 = v47;
        }
        else
        {
          v35 = -1073741811;
          PpfEvtLogTraceHelper(
            (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
            1284,
            (int)"PpfEvtLogWriteDigestTableEntry",
            1,
            "Error: 0x%x",
            13);
        }
        if ( v35 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x524, v36, (const char *)(unsigned int)v35, Formata);
        v30 += 12;
      }
      while ( v30 != v31 );
      v20 = v56;
    }
    LODWORD(v46) = *(_DWORD *)(v19 + 40);
    LODWORD(Size) = v21;
    v40 = PpfEvtLogAddEventAndMovePast(
            (int)v49,
            v27,
            *(_DWORD *)(v19 + 4),
            *(_DWORD *)v19,
            v29,
            Size,
            *(void **)(v19 + 32),
            v46);
    if ( v40 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x52A, v41, (const char *)(unsigned int)v40, Formata);
    v42 = GetProcessHeap();
    HeapFree(v42, 0, v29);
    v19 += 56;
  }
  *v59 = v50;
  *v60 = v48;
}

```

## disassembly

```asm
0x18002cb38  mov     [rsp-8+arg_10], r8
0x18002cb3d  mov     [rsp-8+arg_8], rdx
0x18002cb42  push    rbp
0x18002cb43  push    rbx
0x18002cb44  push    rsi
0x18002cb45  push    rdi
0x18002cb46  push    r12
0x18002cb48  push    r13
0x18002cb4a  push    r14
0x18002cb4c  push    r15
0x18002cb4e  lea     rbp, [rsp-1Fh]
0x18002cb53  sub     rsp, 0A8h
0x18002cb5a  mov     r14, rcx
0x18002cb5d  xor     r9d, r9d
0x18002cb60  mov     [rbp+57h+arg_0], r9d
0x18002cb64  xor     esi, esi
0x18002cb66  mov     rbx, [rcx+8]
0x18002cb6a  mov     r12, [rcx+10h]
0x18002cb6e  cmp     rbx, r12
0x18002cb71  jz      short loc_18002CBD4
0x18002cb73  mov     rdi, [rbx+8]
0x18002cb77  mov     r15, [rbx+10h]
0x18002cb7b  jmp     short loc_18002CB99
0x18002cb7d  lea     rdx, [rbp+57h+arg_0]
0x18002cb81  movzx   ecx, word ptr [rdi]
0x18002cb84  call    PpfEvtLogAccumulateDigestTableSize
0x18002cb89  mov     rcx, [rbp+5Fh]; this
0x18002cb8d  test    eax, eax
0x18002cb8f  js      loc_18002CF61
0x18002cb95  add     rdi, 18h
0x18002cb99  cmp     rdi, r15
0x18002cb9c  jnz     short loc_18002CB7D
0x18002cb9e  mov     edx, esi
0x18002cba0  mov     ecx, [rbx+28h]
0x18002cba3  add     ecx, esi
0x18002cba5  or      eax, 0FFFFFFFFh
0x18002cba8  cmp     ecx, esi
0x18002cbaa  cmovnb  eax, ecx
0x18002cbad  mov     esi, eax
0x18002cbaf  cmp     ecx, edx
0x18002cbb1  sbb     r9d, r9d
0x18002cbb4  and     r9d, 80070216h; char *
0x18002cbbb  mov     rax, [rbp+5Fh]
0x18002cbbf  cmp     ecx, edx
0x18002cbc1  jb      loc_18002CF6F
0x18002cbc7  add     rbx, 38h ; '8'
0x18002cbcb  cmp     rbx, r12
0x18002cbce  jnz     short loc_18002CB73
0x18002cbd0  mov     r9d, [rbp+57h+arg_0]
0x18002cbd4  mov     [rbp+57h+var_78], 0
0x18002cbdc  mov     [rbp+57h+var_88], 0
0x18002cbe3  mov     qword ptr [rbp+57h+var_80], 0
0x18002cbeb  lea     rax, [rbp+57h+var_78]
0x18002cbef  mov     [rbp+57h+var_70], rax
0x18002cbf3  mov     [rbp+57h+var_68], 0
0x18002cbfb  mov     [rbp+57h+var_60], 1
0x18002cbff  mov     r8, [r14+10h]
0x18002cc03  sub     r8, [r14+8]
0x18002cc07  sar     r8, 3
0x18002cc0b  mov     rax, 6DB6DB6DB6DB6DB7h
0x18002cc15  imul    r8, rax
0x18002cc19  lea     rax, [rbp+57h+var_80]
0x18002cc1d  mov     [rsp+0E0h+var_A0], rax
0x18002cc22  lea     rax, [rbp+57h+var_88]
0x18002cc26  mov     [rsp+0E0h+var_A8], rax
0x18002cc2b  lea     rax, [rbp+57h+var_68]
0x18002cc2f  mov     [rsp+0E0h+var_B0], rax
0x18002cc34  mov     dword ptr [rsp+0E0h+Size], 0
0x18002cc3c  mov     dword ptr [rsp+0E0h+Format], esi; int
0x18002cc40  mov     edx, [r14+4]
0x18002cc44  movzx   ecx, word ptr [r14]
0x18002cc48  call    PpfEvtLogAllocateAndInitializeHeader
0x18002cc4d  mov     rcx, [rbp+5Fh]; this
0x18002cc51  test    eax, eax
0x18002cc53  js      loc_18002CF53
0x18002cc59  cmp     [rbp+57h+var_60], 0
0x18002cc5d  jz      short loc_18002CC92
0x18002cc5f  mov     rcx, [rbp+57h+var_70]
0x18002cc63  mov     rbx, [rcx]
0x18002cc66  mov     rax, [rbp+57h+var_68]
0x18002cc6a  mov     [rcx], rax
0x18002cc6d  test    rbx, rbx
0x18002cc70  jz      short loc_18002CC92
0x18002cc72  call    cs:__imp_GetProcessHeap
0x18002cc79  nop     dword ptr [rax+rax+00h]
0x18002cc7e  mov     rcx, rax; hHeap
0x18002cc81  mov     r8, rbx; lpMem
0x18002cc84  xor     edx, edx; dwFlags
0x18002cc86  call    cs:__imp_HeapFree
0x18002cc8d  nop     dword ptr [rax+rax+00h]
0x18002cc92  mov     rsi, [r14+8]
0x18002cc96  mov     r12, [r14+10h]
0x18002cc9a  mov     [rbp+57h+var_48], r12
0x18002cc9e  jmp     loc_18002CF01
0x18002cca3  mov     [rbp+57h+var_58], 0
0x18002ccab  xor     r13d, r13d
0x18002ccae  mov     [rbp+57h+arg_0], r13d
0x18002ccb2  mov     rbx, [rsi+8]
0x18002ccb6  mov     rdi, [rsi+10h]
0x18002ccba  cmp     rbx, rdi
0x18002ccbd  jz      short loc_18002CCE4
0x18002ccbf  lea     rdx, [rbp+57h+arg_0]
0x18002ccc3  movzx   ecx, word ptr [rbx]
0x18002ccc6  call    PpfEvtLogAccumulateDigestTableSize
0x18002cccb  mov     rcx, [rbp+5Fh]; this
0x18002cccf  test    eax, eax
0x18002ccd1  js      loc_18002CF84
0x18002ccd7  add     rbx, 18h
0x18002ccdb  cmp     rbx, rdi
0x18002ccde  jnz     short loc_18002CCBF
0x18002cce0  mov     r13d, [rbp+57h+arg_0]
0x18002cce4  call    cs:__imp_GetProcessHeap
0x18002cceb  nop     dword ptr [rax+rax+00h]
0x18002ccf0  mov     r8d, r13d; dwBytes
0x18002ccf3  xor     edx, edx; dwFlags
0x18002ccf5  mov     rcx, rax; hHeap
0x18002ccf8  call    cs:__imp_HeapAlloc
0x18002ccff  nop     dword ptr [rax+rax+00h]
0x18002cd04  mov     r15, rax
0x18002cd07  mov     [rbp+57h+var_58], rax
0x18002cd0b  mov     rcx, [rbp+5Fh]; this
0x18002cd0f  test    rax, rax
0x18002cd12  jz      loc_18002CF41
0x18002cd18  mov     r14, [rsi+8]
0x18002cd1c  mov     rbx, [rsi+10h]
0x18002cd20  mov     [rbp+57h+var_90], rbx
0x18002cd24  cmp     r14, rbx
0x18002cd27  jz      loc_18002CEAB
0x18002cd2d  xor     eax, eax
0x18002cd2f  mov     [rbp+57h+arg_18], eax
0x18002cd32  mov     rcx, [r14+8]
0x18002cd36  mov     [rbp+57h+Src], rcx
0x18002cd3a  xor     eax, eax
0x18002cd3c  mov     word ptr [rbp+57h+arg_0], ax
0x18002cd40  test    rcx, rcx
0x18002cd43  jz      loc_18002CE59
0x18002cd49  movzx   r12d, word ptr [r14+10h]
0x18002cd4e  movzx   ebx, word ptr [r14]
0x18002cd52  lea     rdx, [rbp+57h+arg_0]
0x18002cd56  movzx   ecx, bx
0x18002cd59  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x18002cd5e  mov     edi, eax
0x18002cd60  test    eax, eax
0x18002cd62  jns     short loc_18002CD9B
0x18002cd64  mov     edx, 509h; int
0x18002cd69  mov     dword ptr [rsp+0E0h+Size], eax; char
0x18002cd6d  lea     rax, aError0xX; "Error: 0x%x"
0x18002cd74  lea     r8, aPpfevtlogwrite; "PpfEvtLogWriteDigestTableEntry"
0x18002cd7b  mov     r9d, 1; int
0x18002cd81  mov     [rsp+0E0h+Format], rax; Format
0x18002cd86  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x18002cd8d  call    PpfEvtLogTraceHelper
0x18002cd92  mov     rbx, [rbp+57h+var_90]
0x18002cd96  jmp     loc_18002CE8E
0x18002cd9b  cmp     word ptr [rbp+57h+arg_0], r12w
0x18002cda0  jz      short loc_18002CDB7
0x18002cda2  mov     r12d, 0C000000Dh
0x18002cda8  mov     edi, r12d
0x18002cdab  mov     dword ptr [rsp+0E0h+Size], r12d
0x18002cdb0  mov     edx, 50Dh
0x18002cdb5  jmp     short loc_18002CD6D
0x18002cdb7  lea     eax, [r12+2]
0x18002cdbc  cmp     eax, 2
0x18002cdbf  jb      loc_18002CE48
0x18002cdc5  mov     edx, [rbp+57h+arg_18]
0x18002cdc8  lea     ecx, [rax+rdx]
0x18002cdcb  cmp     ecx, edx
0x18002cdcd  jb      short loc_18002CE30
0x18002cdcf  cmp     ecx, r13d
0x18002cdd2  jbe     short loc_18002CDE9
0x18002cdd4  mov     r12d, 0C000000Dh
0x18002cdda  mov     edi, r12d
0x18002cddd  mov     dword ptr [rsp+0E0h+Size], r12d
0x18002cde2  mov     edx, 51Fh
0x18002cde7  jmp     short loc_18002CD6D
0x18002cde9  add     rax, r15
0x18002cdec  cmp     rax, r15
0x18002cdef  jb      short loc_18002CE18
0x18002cdf1  xor     edi, edi
0x18002cdf3  mov     [rdx+r15], bx
0x18002cdf8  lea     ebx, [rdx+2]
0x18002cdfb  mov     r8, r12; Size
0x18002cdfe  mov     ecx, ebx
0x18002ce00  add     rcx, r15; void *
0x18002ce03  mov     rdx, [rbp+57h+Src]; Src
0x18002ce07  call    memcpy_0
0x18002ce0c  lea     eax, [rbx+r12]
0x18002ce10  mov     [rbp+57h+arg_18], eax
0x18002ce13  jmp     loc_18002CD92
0x18002ce18  mov     r12d, 0C0000095h
0x18002ce1e  mov     edi, r12d
0x18002ce21  mov     dword ptr [rsp+0E0h+Size], r12d
0x18002ce26  mov     edx, 528h
0x18002ce2b  jmp     loc_18002CD6D
0x18002ce30  mov     r12d, 0C0000095h
0x18002ce36  mov     edi, r12d
0x18002ce39  mov     dword ptr [rsp+0E0h+Size], r12d
0x18002ce3e  mov     edx, 51Ch
0x18002ce43  jmp     loc_18002CD6D
0x18002ce48  mov     eax, 0C0000095h
0x18002ce4d  mov     edi, eax
0x18002ce4f  mov     edx, 517h
0x18002ce54  jmp     loc_18002CD69
0x18002ce59  mov     eax, 0C000000Dh
0x18002ce5e  mov     edi, eax
0x18002ce60  mov     dword ptr [rsp+0E0h+Size], eax; char
0x18002ce64  lea     rax, aError0xX; "Error: 0x%x"
0x18002ce6b  mov     [rsp+0E0h+Format], rax; int
0x18002ce70  mov     r9d, 1; int
0x18002ce76  lea     r8, aPpfevtlogwrite; "PpfEvtLogWriteDigestTableEntry"
0x18002ce7d  mov     edx, 504h; int
0x18002ce82  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x18002ce89  call    PpfEvtLogTraceHelper
0x18002ce8e  mov     rcx, [rbp+5Fh]; this
0x18002ce92  test    edi, edi
0x18002ce94  js      loc_18002CF92
0x18002ce9a  add     r14, 18h
0x18002ce9e  cmp     r14, rbx
0x18002cea1  jnz     loc_18002CD32
0x18002cea7  mov     r12, [rbp+57h+var_48]
0x18002ceab  mov     eax, [rsi+28h]
0x18002ceae  mov     dword ptr [rsp+0E0h+var_A8], eax; size_t
0x18002ceb2  mov     rax, [rsi+20h]
0x18002ceb6  mov     [rsp+0E0h+var_B0], rax; void *
0x18002cebb  mov     dword ptr [rsp+0E0h+Size], r13d; Size
0x18002cec0  mov     [rsp+0E0h+Format], r15; int
0x18002cec5  mov     r9d, [rsi]; int
0x18002cec8  mov     r8d, [rsi+4]; int
0x18002cecc  lea     rcx, [rbp+57h+var_80]; int
0x18002ced0  call    PpfEvtLogAddEventAndMovePast
0x18002ced5  mov     rcx, [rbp+5Fh]; this
0x18002ced9  test    eax, eax
0x18002cedb  js      short loc_18002CF33
0x18002cedd  call    cs:__imp_GetProcessHeap
0x18002cee4  nop     dword ptr [rax+rax+00h]
0x18002cee9  mov     rcx, rax; hHeap
0x18002ceec  mov     r8, r15; lpMem
0x18002ceef  xor     edx, edx; dwFlags
0x18002cef1  call    cs:__imp_HeapFree
0x18002cef8  nop     dword ptr [rax+rax+00h]
0x18002cefd  add     rsi, 38h ; '8'
0x18002cf01  cmp     rsi, r12
0x18002cf04  jnz     loc_18002CCA3
0x18002cf0a  mov     rax, [rbp+57h+var_78]
0x18002cf0e  mov     rcx, [rbp+57h+arg_8]
0x18002cf12  mov     [rcx], rax
0x18002cf15  mov     eax, [rbp+57h+var_88]
0x18002cf18  mov     rcx, [rbp+57h+arg_10]
0x18002cf1c  mov     [rcx], eax
0x18002cf1e  add     rsp, 0A8h
0x18002cf25  pop     r15
0x18002cf27  pop     r14
0x18002cf29  pop     r13
0x18002cf2b  pop     r12
0x18002cf2d  pop     rdi
0x18002cf2e  pop     rsi
0x18002cf2f  pop     rbx
0x18002cf30  pop     rbp
0x18002cf31  retn
0x18002cf33  mov     r9d, eax; char *
0x18002cf36  mov     edx, 52Ah; void *
0x18002cf3b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cf41  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002cf48  mov     edx, 51Fh; void *
0x18002cf4d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002cf53  mov     r9d, eax; char *
0x18002cf56  mov     edx, 513h; void *
0x18002cf5b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cf61  mov     r9d, eax; char *
0x18002cf64  mov     edx, 508h; void *
0x18002cf69  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cf6f  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002cf76  mov     edx, 50Ah; void *
0x18002cf7b  mov     rcx, rax; this
0x18002cf7e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002cf84  mov     r9d, eax; char *
0x18002cf87  mov     edx, 51Ch; void *
0x18002cf8c  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cf92  mov     r9d, edi; char *
0x18002cf95  mov     edx, 524h; void *
0x18002cf9a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
