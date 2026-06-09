# IkeConstructHdr

- ea: `0x180038230`
- end: `0x180038535`
- name: `IkeConstructHdr`
- size: `773`
- prototype: ``
- caller_count: `29`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003fa20`
- `0x1800416f0`
- `0x18004b818`
- `0x1800c2280`
- `0x1800c2618`
- `0x1800c2d68`
- `0x1800c30dc`
- `0x1800c3834`
- `0x1800c3b20`
- `0x1800c3eb4`
- `0x1800c459c`
- `0x1800c9be0`
- `0x1800d44f0`
- `0x1800d49d0`
- `0x1800d4b7c`
- `0x1800d4d8c`
- `0x1800dcad8`
- `0x1800dceb4`
- `0x1800dd194`
- `0x1800dd38c`
- `0x1800dd564`
- `0x1800dd994`
- `0x1800ddbe8`
- `0x1800eedd0`
- `0x1800ef0d8`
- `0x180108c04`
- `0x180108f38`
- `0x18010935c`
- `0x180109764`

## callees

- `0x180008388`
- `0x1800096c0`
- `0x180038230`
- `0x180050850`
- `0x18005bc40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800382b5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800382ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038350`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038395`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800382b5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800382ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038350`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180038395`
- `ntdll!EtwEventWriteTransfer` at `0x18003846f`
- `ntdll!EtwEventWriteTransfer` at `0x18003846f`

## pseudocode

```c
__int64 __fastcall IkeConstructHdr(_DWORD *a1, __int64 *a2, _QWORD *a3, _QWORD *a4, char a5, int a6, char a7)
{
  _QWORD *v11; // rcx
  LPCRITICAL_SECTION v12; // rdx
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v15; // r8
  __int64 v16; // rdi
  DWORD v17; // eax
  __int64 *v18; // rax
  __int64 v19; // r9
  LPCRITICAL_SECTION v20; // rax
  DWORD v21; // ecx
  __int64 *v22; // rax
  __int64 v23; // rcx
  DWORD v24; // ecx
  char *v25; // rax
  const WCHAR *v26; // rdx
  __int64 v27; // rax
  bool v28; // zf
  int v29; // eax
  char v30; // al
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int128 v34; // xmm1
  __int64 v36; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v37[28]; // [rsp+48h] [rbp-61h] BYREF
  char *v38; // [rsp+68h] [rbp-41h] BYREF
  int v39; // [rsp+70h] [rbp-39h]
  int v40; // [rsp+74h] [rbp-35h]
  __int64 *v41; // [rsp+78h] [rbp-31h]
  int v42; // [rsp+80h] [rbp-29h]
  int v43; // [rsp+84h] [rbp-25h]
  __int64 *v44; // [rsp+88h] [rbp-21h]
  __int64 v45; // [rsp+90h] [rbp-19h]
  const WCHAR *v46; // [rsp+98h] [rbp-11h]
  int v47; // [rsp+A0h] [rbp-9h]
  int v48; // [rsp+A4h] [rbp-5h]
  const char *v49; // [rsp+A8h] [rbp-1h]
  __int64 v50; // [rsp+B0h] [rbp+7h]

  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v12 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
    {
      v15 = 0;
    }
    else
    {
      Value = TlsGetValue(LockSemaphore);
      v11 = WPP_GLOBAL_Control;
      v15 = Value;
      v12 = gIkeExtGlobals;
    }
    v16 = (__int64)v15 + 8;
    if ( !v15 )
      v16 = 0;
    if ( v12
      && (v17 = (DWORD)v12[86].LockSemaphore, v17 != -1)
      && (v18 = (__int64 *)TlsGetValue(v17), v11 = WPP_GLOBAL_Control, v18) )
    {
      v19 = *v18;
    }
    else
    {
      LODWORD(v19) = 0;
    }
    WPP_SF_iS(v11[2], 10, (unsigned int)WPP_b4c0bdae5de2357ade4f23a969f1f973_Traceguids, v19, v16);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v20 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v21 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v21 != -1 )
      {
        v22 = (__int64 *)TlsGetValue(v21);
        if ( v22 )
        {
          v23 = *v22;
          v20 = gIkeExtGlobals;
LABEL_23:
          v36 = v23;
          v44 = &v36;
          v45 = 8;
          if ( !v20 )
            goto LABEL_31;
          v24 = (DWORD)v20[86].LockSemaphore;
          if ( v24 == -1 )
            goto LABEL_31;
          v25 = (char *)TlsGetValue(v24);
          v26 = (const WCHAR *)(v25 + 8);
          if ( !v25 )
            v26 = 0;
          if ( v26 )
          {
            v27 = -1;
            do
              v28 = v26[++v27] == 0;
            while ( !v28 );
            v29 = 2 * v27 + 2;
          }
          else
          {
LABEL_31:
            v26 = &LocaleName;
            v29 = 2;
          }
          v47 = v29;
          v46 = v26;
          v49 = "Construct IKEHeader";
          v38 = off_180173280;
          v48 = 0;
          v50 = 20;
          *(_OWORD *)v37 = 0x40B000000uLL;
          v39 = *(unsigned __int16 *)off_180173280;
          v41 = qword_18015A868;
          v40 = 2;
          v42 = 50;
          v43 = 1;
          EtwEventWriteTransfer(qword_180173298, v37, 0, 0, 5, &v38);
          goto LABEL_33;
        }
        v20 = gIkeExtGlobals;
      }
    }
    v23 = 0;
    goto LABEL_23;
  }
LABEL_33:
  v28 = *a1 == 2;
  *(_QWORD *)v37 = *a3;
  *(_QWORD *)&v37[8] = *a4;
  v30 = 16;
  if ( v28 )
    v30 = 32;
  v37[16] = 0;
  v37[17] = v30;
  v37[19] = a7;
  v37[18] = a5;
  *(_DWORD *)&v37[20] = a6;
  *(_DWORD *)&v37[24] = 0;
  v31 = IkeExpandPacket(a2, 28);
  if ( !v31 )
  {
    v32 = *((unsigned __int16 *)a2 + 6);
    v33 = *a2;
    v34 = *(_OWORD *)&v37[12];
    *(_OWORD *)(v32 + v33) = *(_OWORD *)v37;
    *(_OWORD *)(v32 + v33 + 12) = v34;
    LOWORD(v32) = *((_WORD *)a2 + 6);
    *((_WORD *)a2 + 6) = v32 + 28;
    *((_WORD *)a2 + 7) = v32 + 16;
  }
  return IkeReturnError(v31, "IkeConstructHdr");
}

```

## disassembly

```asm
0x180038230  mov     r11, rsp
0x180038233  push    rbp
0x180038234  push    rbx
0x180038235  lea     rbp, [r11-47h]
0x180038239  sub     rsp, 0D8h
0x180038240  mov     rax, cs:__security_cookie
0x180038247  xor     rax, rsp
0x18003824a  mov     [rbp+3Fh+var_30], rax
0x18003824e  mov     [r11+8], rsi
0x180038252  mov     rbx, rdx
0x180038255  mov     [r11-18h], r12
0x180038259  mov     rsi, r9
0x18003825c  mov     [r11-20h], r14
0x180038260  mov     r14, r8
0x180038263  mov     [r11-28h], r15
0x180038267  mov     r15, rcx
0x18003826a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038271  lea     rax, WPP_GLOBAL_Control
0x180038278  xor     r12d, r12d
0x18003827b  cmp     rcx, rax
0x18003827e  jz      loc_18003832A
0x180038284  cmp     byte ptr [rcx+19h], 4
0x180038288  jb      loc_18003832A
0x18003828e  test    byte ptr [rcx+1Ch], 10h
0x180038292  jz      loc_18003832A
0x180038298  mov     rdx, cs:gIkeExtGlobals
0x18003829f  mov     [r11+18h], rdi
0x1800382a3  test    rdx, rdx
0x1800382a6  jz      short loc_1800382CE
0x1800382a8  mov     eax, [rdx+0D88h]
0x1800382ae  cmp     eax, 0FFFFFFFFh
0x1800382b1  jz      short loc_1800382CE
0x1800382b3  mov     ecx, eax; dwTlsIndex
0x1800382b5  call    cs:__imp_TlsGetValue
0x1800382bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382c2  mov     r8, rax
0x1800382c5  mov     rdx, cs:gIkeExtGlobals
0x1800382cc  jmp     short loc_1800382D1
0x1800382ce  mov     r8, r12
0x1800382d1  test    r8, r8
0x1800382d4  lea     rdi, [r8+8]
0x1800382d8  cmovz   rdi, r12
0x1800382dc  test    rdx, rdx
0x1800382df  jz      short loc_180038305
0x1800382e1  mov     eax, [rdx+0D88h]
0x1800382e7  cmp     eax, 0FFFFFFFFh
0x1800382ea  jz      short loc_180038305
0x1800382ec  mov     ecx, eax; dwTlsIndex
0x1800382ee  call    cs:__imp_TlsGetValue
0x1800382f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382fb  test    rax, rax
0x1800382fe  jz      short loc_180038305
0x180038300  mov     r9, [rax]
0x180038303  jmp     short loc_180038308
0x180038305  mov     r9, r12
0x180038308  mov     rcx, [rcx+10h]
0x18003830c  lea     r8, WPP_b4c0bdae5de2357ade4f23a969f1f973_Traceguids
0x180038313  mov     edx, 0Ah
0x180038318  mov     [rsp+0E0h+var_C0], rdi
0x18003831d  call    WPP_SF_iS
0x180038322  mov     rdi, [rsp+0E0h+arg_10]
0x18003832a  mov     eax, cs:dword_180173278
0x180038330  cmp     eax, 4
0x180038333  jbe     loc_180038475
0x180038339  mov     rax, cs:gIkeExtGlobals
0x180038340  test    rax, rax
0x180038343  jz      short loc_18003836E
0x180038345  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003834b  cmp     ecx, 0FFFFFFFFh
0x18003834e  jz      short loc_18003836E
0x180038350  call    cs:__imp_TlsGetValue
0x180038356  test    rax, rax
0x180038359  jz      short loc_180038367
0x18003835b  mov     rcx, [rax]
0x18003835e  mov     rax, cs:gIkeExtGlobals
0x180038365  jmp     short loc_180038371
0x180038367  mov     rax, cs:gIkeExtGlobals
0x18003836e  mov     rcx, r12
0x180038371  mov     [rbp+3Fh+var_A8], rcx
0x180038375  lea     rcx, [rbp+3Fh+var_A8]
0x180038379  mov     [rbp+3Fh+var_60], rcx
0x18003837d  mov     [rbp+3Fh+var_58], 8
0x180038385  test    rax, rax
0x180038388  jz      short loc_1800383C7
0x18003838a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180038390  cmp     ecx, 0FFFFFFFFh
0x180038393  jz      short loc_1800383C7
0x180038395  call    cs:__imp_TlsGetValue
0x18003839b  test    rax, rax
0x18003839e  lea     rdx, [rax+8]
0x1800383a2  cmovz   rdx, r12
0x1800383a6  test    rdx, rdx
0x1800383a9  jz      short loc_1800383C7
0x1800383ab  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800383b2  cmp     [rdx+rax*2+2], r12w
0x1800383b8  lea     rax, [rax+1]
0x1800383bc  jnz     short loc_1800383B2
0x1800383be  lea     eax, ds:2[rax*2]
0x1800383c5  jmp     short loc_1800383D3
0x1800383c7  lea     rdx, LocaleName
0x1800383ce  mov     eax, 2
0x1800383d3  mov     [rbp+3Fh+var_48], eax
0x1800383d6  lea     rcx, _TraceLoggingMetadata
0x1800383dd  mov     [rbp+3Fh+var_50], rdx
0x1800383e1  lea     rax, aConstructIkehe; "Construct IKEHeader"
0x1800383e8  mov     [rbp+3Fh+var_40], rax
0x1800383ec  lea     rdx, [rbp+3Fh+var_A0]
0x1800383f0  movzx   eax, cs:word_18015A85E
0x1800383f7  xor     r9d, r9d
0x1800383fa  mov     dword ptr [rbp+3Fh+var_A0+4], eax
0x1800383fd  xor     r8d, r8d
0x180038400  mov     rax, cs:off_180173280
0x180038407  mov     [rbp+3Fh+var_80], rax
0x18003840b  mov     [rbp+3Fh+var_44], r12d
0x18003840f  mov     [rbp+3Fh+var_38], 14h
0x180038417  mov     dword ptr [rbp+3Fh+var_A0], 0B000000h
0x18003841e  mov     qword ptr [rbp+3Fh+var_A0+8], r12
0x180038422  movzx   eax, word ptr [rax]
0x180038425  mov     [rbp+3Fh+var_78], eax
0x180038428  lea     rax, qword_18015A868
0x18003842f  mov     [rbp+3Fh+var_70], rax
0x180038433  lea     rax, _TraceLoggingMetadataEnd
0x18003843a  sub     eax, ecx
0x18003843c  mov     [rbp+3Fh+var_74], 2
0x180038443  mov     [rbp+3Fh+var_68], 32h ; '2'
0x18003844a  mov     [rbp+3Fh+var_64], 1
0x180038451  mov     [rbp+3Fh+var_B0], eax
0x180038454  mov     eax, [rbp+3Fh+var_B0]
0x180038457  mov     rcx, cs:qword_180173298
0x18003845e  lea     rax, [rbp+3Fh+var_80]
0x180038462  mov     [rsp+28h], rax
0x180038467  mov     dword ptr [rsp+0E0h+var_C0], 5
0x18003846f  call    cs:__imp_EtwEventWriteTransfer
0x180038475  mov     rax, [r14]
0x180038478  mov     ecx, 20h ; ' '
0x18003847d  cmp     dword ptr [r15], 2
0x180038481  mov     edx, 1Ch
0x180038486  mov     qword ptr [rbp+3Fh+var_A0], rax
0x18003848a  mov     rax, [rsi]
0x18003848d  mov     qword ptr [rbp+3Fh+var_A0+8], rax
0x180038491  mov     eax, 10h
0x180038496  cmovz   eax, ecx
0x180038499  mov     [rbp+3Fh+var_90], r12b
0x18003849d  mov     [rbp+3Fh+var_8F], al
0x1800384a0  mov     rcx, rbx
0x1800384a3  movzx   eax, [rbp+3Fh+arg_30]
0x1800384a7  mov     [rbp+3Fh+var_8D], al
0x1800384aa  movzx   eax, [rbp+3Fh+arg_20]
0x1800384ae  mov     [rbp+3Fh+var_8E], al
0x1800384b1  mov     eax, [rbp+3Fh+arg_28]
0x1800384b4  mov     [rbp+3Fh+var_8C], eax
0x1800384b7  mov     [rbp+3Fh+var_88], r12d
0x1800384bb  call    IkeExpandPacket
0x1800384c0  mov     r15, [rsp+0E0h+var_20]
0x1800384c8  mov     r14, [rsp+0E0h+var_18]
0x1800384d0  mov     r12, [rsp+0D0h]
0x1800384d8  mov     rsi, [rsp+0E0h+arg_0]
0x1800384e0  test    rax, rax
0x1800384e3  jnz     short loc_180038510
0x1800384e5  movzx   edx, word ptr [rbx+0Ch]
0x1800384e9  mov     rcx, [rbx]
0x1800384ec  movups  xmm0, [rbp+3Fh+var_A0]
0x1800384f0  movups  xmm1, [rbp+3Fh+var_A0+0Ch]
0x1800384f4  movups  xmmword ptr [rdx+rcx], xmm0
0x1800384f8  movups  xmmword ptr [rdx+rcx+0Ch], xmm1
0x1800384fd  movzx   edx, word ptr [rbx+0Ch]
0x180038501  lea     ecx, [rdx+10h]
0x180038504  add     dx, 1Ch
0x180038508  mov     [rbx+0Ch], dx
0x18003850c  mov     [rbx+0Eh], cx
0x180038510  lea     rdx, aIkeconstructhd; "IkeConstructHdr"
0x180038517  mov     rcx, rax
0x18003851a  call    IkeReturnError
0x18003851f  mov     rcx, [rbp+3Fh+var_30]
0x180038523  xor     rcx, rsp; StackCookie
0x180038526  call    __security_check_cookie
0x18003852b  add     rsp, 0D8h
0x180038532  pop     rbx
0x180038533  pop     rbp
0x180038534  retn
```
