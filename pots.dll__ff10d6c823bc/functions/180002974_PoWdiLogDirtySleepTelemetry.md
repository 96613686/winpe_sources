# PoWdiLogDirtySleepTelemetry

- ea: `0x180002974`
- end: `0x180002e48`
- name: `PoWdiLogDirtySleepTelemetry`
- size: `1236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004710`

## callees

- `0x18000113c`
- `0x180001f6c`
- `0x1800024e8`
- `0x180002974`
- `0x180004930`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180002a57`
- `msvcrt!swprintf_s` at `0x180002a76`
- `msvcrt!swprintf_s` at `0x180002a8c`
- `msvcrt!swprintf_s` at `0x180002aa2`
- `msvcrt!swprintf_s` at `0x180002ab8`
- `msvcrt!swprintf_s` at `0x180002ad1`
- `msvcrt!swprintf_s` at `0x180002a57`
- `msvcrt!swprintf_s` at `0x180002a76`
- `msvcrt!swprintf_s` at `0x180002a8c`
- `msvcrt!swprintf_s` at `0x180002aa2`
- `msvcrt!swprintf_s` at `0x180002ab8`
- `msvcrt!swprintf_s` at `0x180002ad1`
- `wdi!WdiSetFeedback` at `0x180002e17`
- `wdi!WdiSetFeedback` at `0x180002e17`

## pseudocode

```c
__int64 __fastcall PoWdiLogDirtySleepTelemetry(__int64 a1, struct _EVENT_RECORD *a2)
{
  __int64 result; // rax
  int v5; // ebx
  int CrashDumpData; // eax
  int v7; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v20; // [rsp+3Ch] [rbp-C4h]
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v23; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[32]; // [rsp+70h] [rbp-90h] BYREF
  int *v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  wchar_t *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  wchar_t *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  wchar_t *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  wchar_t *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  wchar_t *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  wchar_t *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  int *v41; // [rsp+100h] [rbp+0h]
  __int64 v42; // [rsp+108h] [rbp+8h]
  __int128 v43; // [rsp+110h] [rbp+10h]
  __int128 v44; // [rsp+120h] [rbp+20h]
  wchar_t v45[12]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t Buffer[12]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t v47[20]; // [rsp+160h] [rbp+60h] BYREF
  wchar_t v48[20]; // [rsp+188h] [rbp+88h] BYREF
  wchar_t v49[20]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v50[20]; // [rsp+1D8h] [rbp+D8h] BYREF

  v17 = 0;
  v20 = 0;
  v19 = 0;
  result = PoWdiGetULongProperty(a2, L"SleepInProgress", &v19);
  if ( (_DWORD)result && v19 )
  {
    v20 = 0;
    v17 = 0;
    v43 = 0;
    v5 = 0;
    v44 = 0;
    if ( (unsigned int)PoWdiGetULongProperty(a2, L"BootAppStatus", &v17) && v17 )
      v5 = 0x20000;
    CrashDumpData = PoWdiGetCrashDumpData(a2);
    v7 = v5 | 0x8000;
    if ( !CrashDumpData )
      v7 = v5;
    swprintf_s(Buffer, 9u, L"%08X", v20);
    swprintf_s(v47, 0x11u, L"%016IX", (_QWORD)v43);
    swprintf_s(v48, 0x11u, L"%016IX", *((_QWORD *)&v43 + 1));
    swprintf_s(v49, 0x11u, L"%016IX", (_QWORD)v44);
    swprintf_s(v50, 0x11u, L"%016IX", *((_QWORD *)&v44 + 1));
    swprintf_s(v45, 9u, L"%08X", v17);
    v10 = -1;
    if ( v7
      && (unsigned int)dword_1800091A8 > 5
      && (qword_1800091B8 & 0x200000000000LL) != 0
      && (qword_1800091C0 & 0x200000000000LL) == qword_1800091C0 )
    {
      v18 = v7;
      v27 = &v18;
      v11 = -1;
      v28 = 4;
      do
        ++v11;
      while ( Buffer[v11] );
      v29 = Buffer;
      v30 = (unsigned int)(2 * v11 + 2);
      v12 = -1;
      do
        ++v12;
      while ( v47[v12] );
      v31 = v47;
      v32 = (unsigned int)(2 * v12 + 2);
      v13 = -1;
      do
        ++v13;
      while ( v48[v13] );
      v33 = v48;
      v34 = (unsigned int)(2 * v13 + 2);
      v14 = -1;
      do
        ++v14;
      while ( v49[v14] );
      v35 = v49;
      v36 = (unsigned int)(2 * v14 + 2);
      v15 = -1;
      do
        ++v15;
      while ( v50[v15] );
      v37 = v50;
      v38 = (unsigned int)(2 * v15 + 2);
      v16 = -1;
      do
        ++v16;
      while ( v45[v16] );
      v40 = (unsigned int)(2 * v16 + 2);
      v39 = v45;
      tlgWriteTransfer_EtwEventWriteTransfer((__int64)v45, byte_180006D09, v8, v9, 9, (__int64)v26);
    }
    if ( (unsigned int)dword_1800091A8 > 5
      && (qword_1800091B8 & 0x400000000000LL) != 0
      && (qword_1800091C0 & 0x400000000000LL) == qword_1800091C0 )
    {
      v18 = 4;
      v27 = &v18;
      v21 = v19;
      v29 = (wchar_t *)&v21;
      v31 = (wchar_t *)&v22;
      v28 = 4;
      v30 = 4;
      v22 = v7;
      v32 = 4;
      do
        ++v10;
      while ( v45[v10] );
      v33 = v45;
      v34 = (unsigned int)(2 * v10 + 2);
      tlgWriteTransfer_EtwEventWriteTransfer(qword_1800091C0, byte_180006E8A, v8, v9, 6, (__int64)v26);
    }
    if ( (unsigned int)dword_1800091A8 > 5
      && (qword_1800091B8 & 0x400000000000LL) != 0
      && (qword_1800091C0 & 0x400000000000LL) == qword_1800091C0 )
    {
      v22 = v19;
      v27 = &v22;
      v29 = (wchar_t *)&v21;
      v18 = v20;
      v31 = (wchar_t *)&v18;
      v24 = v43;
      v33 = (wchar_t *)&v24;
      v35 = (wchar_t *)&v24 + 4;
      v25 = v44;
      v37 = (wchar_t *)&v25;
      v39 = (wchar_t *)&v25 + 4;
      v23 = v17;
      v41 = (int *)&v23;
      v28 = 4;
      v21 = v7;
      v30 = 4;
      v32 = 4;
      v34 = 8;
      v36 = 8;
      v38 = 8;
      v40 = 8;
      v42 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(qword_1800091C0, byte_18000717F, v8, v9, 10, (__int64)v26);
    }
    return WdiSetFeedback(a1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180002974  mov     [rsp-8+arg_10], rbx
0x180002979  mov     [rsp-8+arg_18], rsi
0x18000297e  push    rbp
0x18000297f  push    rdi
0x180002980  push    r12
0x180002982  push    r14
0x180002984  push    r15
0x180002986  lea     rbp, [rsp-110h]
0x18000298e  sub     rsp, 210h
0x180002995  mov     rax, cs:__security_cookie
0x18000299c  xor     rax, rsp
0x18000299f  mov     [rbp+130h+var_30], rax
0x1800029a6  mov     rdi, rdx
0x1800029a9  lea     r8, [rsp+230h+var_1F8]
0x1800029ae  xor     r15d, r15d
0x1800029b1  lea     rdx, aSleepinprogres; "SleepInProgress"
0x1800029b8  mov     rsi, rcx
0x1800029bb  mov     [rsp+230h+var_200], r15d
0x1800029c0  mov     rcx, rdi
0x1800029c3  mov     [rsp+230h+var_1F4], r15d
0x1800029c8  mov     [rsp+230h+var_1F8], r15d
0x1800029cd  call    PoWdiGetULongProperty
0x1800029d2  test    eax, eax
0x1800029d4  jz      loc_180002E1D
0x1800029da  cmp     [rsp+230h+var_1F8], r15d
0x1800029df  jz      loc_180002E1D
0x1800029e5  xorps   xmm0, xmm0
0x1800029e8  mov     [rsp+230h+var_1F4], r15d
0x1800029ed  lea     r8, [rsp+230h+var_200]
0x1800029f2  mov     [rsp+230h+var_200], r15d
0x1800029f7  lea     rdx, aBootappstatus; "BootAppStatus"
0x1800029fe  mov     rcx, rdi
0x180002a01  movups  [rbp+130h+var_120], xmm0
0x180002a05  mov     ebx, r15d
0x180002a08  movups  [rbp+130h+var_110], xmm0
0x180002a0c  call    PoWdiGetULongProperty
0x180002a11  test    eax, eax
0x180002a13  jz      short loc_180002A22
0x180002a15  cmp     [rsp+230h+var_200], r15d
0x180002a1a  mov     eax, 20000h
0x180002a1f  cmovnz  ebx, eax
0x180002a22  lea     r8, [rbp+130h+var_120]
0x180002a26  mov     rcx, rdi; pEvent
0x180002a29  lea     rdx, [rsp+230h+var_1F4]
0x180002a2e  call    PoWdiGetCrashDumpData
0x180002a33  mov     r9d, [rsp+230h+var_1F4]
0x180002a38  lea     r8, a08x; "%08X"
0x180002a3f  mov     edi, ebx
0x180002a41  lea     rcx, [rbp+130h+Buffer]; Buffer
0x180002a45  bts     edi, 0Fh
0x180002a49  mov     r12d, 9
0x180002a4f  test    eax, eax
0x180002a51  mov     edx, r12d; BufferCount
0x180002a54  cmovz   edi, ebx
0x180002a57  call    cs:__imp_swprintf_s
0x180002a5d  mov     r9, qword ptr [rbp+130h+var_120]
0x180002a61  lea     r14, a016ix; "%016IX"
0x180002a68  lea     ebx, [r12+8]
0x180002a6d  mov     r8, r14; Format
0x180002a70  mov     edx, ebx; BufferCount
0x180002a72  lea     rcx, [rbp+130h+var_D0]; Buffer
0x180002a76  call    cs:__imp_swprintf_s
0x180002a7c  mov     r9, qword ptr [rbp+130h+var_120+8]
0x180002a80  lea     rcx, [rbp+130h+var_A8]; Buffer
0x180002a87  mov     r8, r14; Format
0x180002a8a  mov     edx, ebx; BufferCount
0x180002a8c  call    cs:__imp_swprintf_s
0x180002a92  mov     r9, qword ptr [rbp+130h+var_110]
0x180002a96  lea     rcx, [rbp+130h+var_80]; Buffer
0x180002a9d  mov     r8, r14; Format
0x180002aa0  mov     edx, ebx; BufferCount
0x180002aa2  call    cs:__imp_swprintf_s
0x180002aa8  mov     r9, qword ptr [rbp+130h+var_110+8]
0x180002aac  lea     rcx, [rbp+130h+var_58]; Buffer
0x180002ab3  mov     r8, r14; Format
0x180002ab6  mov     edx, ebx; BufferCount
0x180002ab8  call    cs:__imp_swprintf_s
0x180002abe  mov     r9d, [rsp+230h+var_200]
0x180002ac3  lea     r8, a08x; "%08X"
0x180002aca  mov     edx, r12d; BufferCount
0x180002acd  lea     rcx, [rbp+130h+var_100]; Buffer
0x180002ad1  call    cs:__imp_swprintf_s
0x180002ad7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002adb  lea     r14d, [r12-5]
0x180002ae0  test    edi, edi
0x180002ae2  jz      loc_180002C4F
0x180002ae8  mov     eax, cs:dword_1800091A8
0x180002aee  cmp     eax, 5
0x180002af1  jbe     loc_180002C4F
0x180002af7  mov     rcx, cs:qword_1800091C0
0x180002afe  mov     rdx, 200000000000h
0x180002b08  mov     rax, cs:qword_1800091B8
0x180002b0f  test    rdx, rax
0x180002b12  jz      loc_180002C4F
0x180002b18  mov     rax, rcx
0x180002b1b  and     rax, rdx
0x180002b1e  cmp     rax, rcx
0x180002b21  jnz     loc_180002C4F
0x180002b27  lea     rax, [rsp+230h+var_1FC]
0x180002b2c  mov     [rsp+230h+var_1FC], edi
0x180002b30  mov     [rbp+130h+var_1A0], rax
0x180002b34  lea     rcx, [rbp+130h+Buffer]
0x180002b38  mov     rax, rbx
0x180002b3b  mov     [rbp+130h+var_198], r14
0x180002b3f  inc     rax
0x180002b42  cmp     [rcx+rax*2], r15w
0x180002b47  jnz     short loc_180002B3F
0x180002b49  lea     rcx, [rbp+130h+Buffer]
0x180002b4d  mov     dword ptr [rbp+130h+var_188+4], r15d
0x180002b51  lea     eax, ds:2[rax*2]
0x180002b58  mov     [rbp+130h+var_190], rcx
0x180002b5c  mov     dword ptr [rbp+130h+var_188], eax
0x180002b5f  lea     rcx, [rbp+130h+var_D0]
0x180002b63  mov     rax, rbx
0x180002b66  inc     rax
0x180002b69  cmp     [rcx+rax*2], r15w
0x180002b6e  jnz     short loc_180002B66
0x180002b70  lea     rcx, [rbp+130h+var_D0]
0x180002b74  mov     dword ptr [rbp+130h+var_178+4], r15d
0x180002b78  lea     eax, ds:2[rax*2]
0x180002b7f  mov     [rbp+130h+var_180], rcx
0x180002b83  mov     dword ptr [rbp+130h+var_178], eax
0x180002b86  lea     rcx, [rbp+130h+var_A8]
0x180002b8d  mov     rax, rbx
0x180002b90  inc     rax
0x180002b93  cmp     [rcx+rax*2], r15w
0x180002b98  jnz     short loc_180002B90
0x180002b9a  lea     rcx, [rbp+130h+var_A8]
0x180002ba1  mov     dword ptr [rbp+130h+var_168+4], r15d
0x180002ba5  lea     eax, ds:2[rax*2]
0x180002bac  mov     [rbp+130h+var_170], rcx
0x180002bb0  mov     dword ptr [rbp+130h+var_168], eax
0x180002bb3  lea     rcx, [rbp+130h+var_80]
0x180002bba  mov     rax, rbx
0x180002bbd  inc     rax
0x180002bc0  cmp     [rcx+rax*2], r15w
0x180002bc5  jnz     short loc_180002BBD
0x180002bc7  lea     rcx, [rbp+130h+var_80]
0x180002bce  mov     dword ptr [rbp+130h+var_158+4], r15d
0x180002bd2  lea     eax, ds:2[rax*2]
0x180002bd9  mov     [rbp+130h+var_160], rcx
0x180002bdd  mov     dword ptr [rbp+130h+var_158], eax
0x180002be0  lea     rcx, [rbp+130h+var_58]
0x180002be7  mov     rax, rbx
0x180002bea  inc     rax
0x180002bed  cmp     [rcx+rax*2], r15w
0x180002bf2  jnz     short loc_180002BEA
0x180002bf4  lea     rcx, [rbp+130h+var_58]
0x180002bfb  mov     dword ptr [rbp+130h+var_148+4], r15d
0x180002bff  lea     eax, ds:2[rax*2]
0x180002c06  mov     [rbp+130h+var_150], rcx
0x180002c0a  mov     dword ptr [rbp+130h+var_148], eax
0x180002c0d  lea     rcx, [rbp+130h+var_100]
0x180002c11  mov     rax, rbx
0x180002c14  inc     rax
0x180002c17  cmp     [rcx+rax*2], r15w
0x180002c1c  jnz     short loc_180002C14
0x180002c1e  lea     eax, ds:2[rax*2]
0x180002c25  mov     dword ptr [rbp+130h+var_138+4], r15d
0x180002c29  mov     dword ptr [rbp+130h+var_138], eax
0x180002c2c  lea     rcx, [rbp+130h+var_100]
0x180002c30  lea     rax, [rsp+230h+var_1C0]
0x180002c35  mov     [rbp+130h+var_140], rcx
0x180002c39  mov     [rsp+230h+var_208], rax
0x180002c3e  lea     rdx, byte_180006D09
0x180002c45  mov     [rsp+230h+var_210], r12d
0x180002c4a  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180002c4f  mov     eax, cs:dword_1800091A8
0x180002c55  mov     r12, 400000000000h
0x180002c5f  cmp     eax, 5
0x180002c62  jbe     loc_180002D04
0x180002c68  mov     rcx, cs:qword_1800091C0
0x180002c6f  mov     rax, cs:qword_1800091B8
0x180002c76  test    r12, rax
0x180002c79  jz      loc_180002D04
0x180002c7f  mov     rax, rcx
0x180002c82  and     rax, r12
0x180002c85  cmp     rax, rcx
0x180002c88  jnz     short loc_180002D04
0x180002c8a  lea     rax, [rsp+230h+var_1FC]
0x180002c8f  mov     [rsp+230h+var_1FC], r14d
0x180002c94  mov     [rbp+130h+var_1A0], rax
0x180002c98  mov     eax, [rsp+230h+var_1F8]
0x180002c9c  mov     [rsp+230h+var_1F0], eax
0x180002ca0  lea     rax, [rsp+230h+var_1F0]
0x180002ca5  mov     [rbp+130h+var_190], rax
0x180002ca9  lea     rax, [rsp+230h+var_1EC]
0x180002cae  mov     [rbp+130h+var_180], rax
0x180002cb2  lea     rax, [rbp+130h+var_100]
0x180002cb6  mov     [rbp+130h+var_198], r14
0x180002cba  mov     [rbp+130h+var_188], r14
0x180002cbe  mov     [rsp+230h+var_1EC], edi
0x180002cc2  mov     [rbp+130h+var_178], r14
0x180002cc6  inc     rbx
0x180002cc9  cmp     [rax+rbx*2], r15w
0x180002cce  jnz     short loc_180002CC6
0x180002cd0  lea     rax, [rbp+130h+var_100]
0x180002cd4  mov     dword ptr [rbp+130h+var_168+4], r15d
0x180002cd8  mov     [rbp+130h+var_170], rax
0x180002cdc  lea     rdx, byte_180006E8A
0x180002ce3  lea     eax, ds:2[rbx*2]
0x180002cea  mov     dword ptr [rbp+130h+var_168], eax
0x180002ced  lea     rax, [rsp+230h+var_1C0]
0x180002cf2  mov     [rsp+230h+var_208], rax
0x180002cf7  mov     [rsp+230h+var_210], 6
0x180002cff  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180002d04  mov     eax, cs:dword_1800091A8
0x180002d0a  cmp     eax, 5
0x180002d0d  jbe     loc_180002E0F
0x180002d13  mov     rcx, cs:qword_1800091C0
0x180002d1a  mov     rax, cs:qword_1800091B8
0x180002d21  test    r12, rax
0x180002d24  jz      loc_180002E0F
0x180002d2a  mov     rax, rcx
0x180002d2d  and     rax, r12
0x180002d30  cmp     rax, rcx
0x180002d33  jnz     loc_180002E0F
0x180002d39  mov     eax, [rsp+230h+var_1F8]
0x180002d3d  lea     rdx, byte_18000717F
0x180002d44  mov     [rsp+230h+var_1EC], eax
0x180002d48  lea     rax, [rsp+230h+var_1EC]
0x180002d4d  mov     [rbp+130h+var_1A0], rax
0x180002d51  lea     rax, [rsp+230h+var_1F0]
0x180002d56  mov     [rbp+130h+var_190], rax
0x180002d5a  mov     eax, [rsp+230h+var_1F4]
0x180002d5e  mov     [rsp+230h+var_1FC], eax
0x180002d62  lea     rax, [rsp+230h+var_1FC]
0x180002d67  mov     [rbp+130h+var_180], rax
0x180002d6b  mov     rax, qword ptr [rbp+130h+var_120]
0x180002d6f  mov     qword ptr [rsp+230h+var_1E0], rax
0x180002d74  lea     rax, [rsp+230h+var_1E0]
0x180002d79  mov     [rbp+130h+var_170], rax
0x180002d7d  mov     rax, qword ptr [rbp+130h+var_120+8]
0x180002d81  mov     qword ptr [rsp+230h+var_1E0+8], rax
0x180002d86  lea     rax, [rsp+230h+var_1E0+8]
0x180002d8b  mov     [rbp+130h+var_160], rax
0x180002d8f  mov     rax, qword ptr [rbp+130h+var_110]
0x180002d93  mov     qword ptr [rsp+230h+var_1D0], rax
0x180002d98  lea     rax, [rsp+230h+var_1D0]
0x180002d9d  mov     [rbp+130h+var_150], rax
0x180002da1  mov     rax, qword ptr [rbp+130h+var_110+8]
0x180002da5  mov     qword ptr [rsp+230h+var_1D0+8], rax
0x180002daa  lea     rax, [rsp+230h+var_1D0+8]
0x180002daf  mov     [rbp+130h+var_140], rax
0x180002db3  mov     eax, [rsp+230h+var_200]
0x180002db7  mov     [rsp+230h+var_1E8], eax
0x180002dbb  lea     rax, [rsp+230h+var_1E8]
0x180002dc0  mov     [rbp+130h+var_130], rax
0x180002dc4  lea     rax, [rsp+230h+var_1C0]
0x180002dc9  mov     [rsp+230h+var_208], rax
0x180002dce  mov     [rsp+230h+var_210], 0Ah
0x180002dd6  mov     [rbp+130h+var_198], r14
0x180002dda  mov     [rsp+230h+var_1F0], edi
0x180002dde  mov     [rbp+130h+var_188], r14
0x180002de2  mov     [rbp+130h+var_178], r14
0x180002de6  mov     [rbp+130h+var_168], 8
0x180002dee  mov     [rbp+130h+var_158], 8
0x180002df6  mov     [rbp+130h+var_148], 8
0x180002dfe  mov     [rbp+130h+var_138], 8
0x180002e06  mov     [rbp+130h+var_128], r14
0x180002e0a  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180002e0f  mov     edx, 1
0x180002e14  mov     rcx, rsi
0x180002e17  call    cs:__imp_WdiSetFeedback
0x180002e1d  mov     rcx, [rbp+130h+var_30]
0x180002e24  xor     rcx, rsp; StackCookie
0x180002e27  call    __security_check_cookie
0x180002e2c  lea     r11, [rsp+230h+var_20]
0x180002e34  mov     rbx, [r11+40h]
0x180002e38  mov     rsi, [r11+48h]
0x180002e3c  mov     rsp, r11
0x180002e3f  pop     r15
0x180002e41  pop     r14
0x180002e43  pop     r12
0x180002e45  pop     rdi
0x180002e46  pop     rbp
0x180002e47  retn
```
