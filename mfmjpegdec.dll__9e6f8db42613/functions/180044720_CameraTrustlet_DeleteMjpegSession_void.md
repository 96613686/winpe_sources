# CameraTrustlet::DeleteMjpegSession(void *)

- ea: `0x180044720`
- end: `0x1800448b6`
- name: `?DeleteMjpegSession@CameraTrustlet@@QEAAJPEAX@Z`
- size: `406`
- prototype: `__int64 __fastcall(CameraTrustlet *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003f408`

## callees

- `0x180044720`
- `0x180044ffc`
- `0x180045060`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18004478b`
- `RPCRT4!NdrClientCall3` at `0x18004478b`

## pseudocode

```c
__int64 __fastcall CameraTrustlet::DeleteMjpegSession(CameraTrustlet *this, void *a2, __int64 a3)
{
  int v5; // ebx
  int Pointer; // eax
  __int64 v7; // rdx
  int v9; // [rsp+30h] [rbp-38h]
  __int128 v10; // [rsp+40h] [rbp-28h] BYREF

  if ( a2 )
  {
    v10 = *((_OWORD *)this + 1);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&IFsIsoRpc_ProxyInfo,
                              7u,
                              0,
                              *(_QWORD *)this,
                              &v10).Pointer;
    v5 = Pointer;
    v9 = Pointer;
    if ( Pointer >= 0 )
    {
      *((GUID *)this + 1) = GUID_00000000_0000_0000_0000_000000000000;
      v5 = -2147418113;
      if ( g_wppLevels )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids,
          this,
          -2147418113);
    }
    else if ( g_wppLevels )
    {
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids,
        this,
        Pointer);
    }
  }
  else
  {
    v5 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        &WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids,
        this,
        -2147024809);
  }
  if ( v5 >= 0 )
  {
    if ( (unsigned __int8)byte_18009D825 >= 8u )
    {
      v7 = 56;
      goto LABEL_15;
    }
  }
  else if ( byte_18009D825 )
  {
    v7 = 55;
LABEL_15:
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, a3, this, v5, a2, v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180044720  mov     [rsp+arg_8], rdx
0x180044725  mov     [rsp+arg_0], rcx
0x18004472a  push    rbx
0x18004472b  push    rsi
0x18004472c  push    rdi
0x18004472d  sub     rsp, 50h
0x180044731  mov     rsi, rdx
0x180044734  mov     rdi, rcx
0x180044737  test    rdx, rdx
0x18004473a  jnz     short loc_18004475A
0x18004473c  mov     ebx, 80070057h
0x180044741  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044748  jb      loc_18004486B
0x18004474e  lea     edx, [rsi+33h]
0x180044751  mov     dword ptr [rsp+68h+var_48], ebx
0x180044755  jmp     loc_180044851
0x18004475a  mov     [rsp+68h+arg_10], 0
0x180044766  movups  xmm0, xmmword ptr [rcx+10h]
0x18004476a  movdqu  [rsp+68h+var_28], xmm0
0x180044770  lea     rax, [rsp+68h+var_28]
0x180044775  mov     [rsp+68h+var_48], rax
0x18004477a  mov     r9, [rcx]
0x18004477d  xor     r8d, r8d; pReturnValue
0x180044780  lea     edx, [r8+7]; nProcNum
0x180044784  lea     rcx, ?IFsIsoRpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18004478b  call    cs:__imp_NdrClientCall3
0x180044791  mov     rbx, rax
0x180044794  mov     [rsp+68h+arg_10], rax
0x18004479c  mov     [rsp+68h+var_38], eax
0x1800447a0  test    eax, eax
0x1800447a2  jns     short loc_1800447D5
0x1800447a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800447ab  jb      short loc_1800447D0
0x1800447ad  mov     edx, 34h ; '4'
0x1800447b2  mov     dword ptr [rsp+68h+var_48], eax
0x1800447b6  mov     r9, rdi
0x1800447b9  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x1800447c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800447c7  mov     rcx, [rcx+10h]
0x1800447cb  call    WPP_SF_qd
0x1800447d0  jmp     loc_18004486B
0x1800447d5  jmp     short loc_18004482C
0x1800447d7  test    eax, eax
0x1800447d9  jz      short loc_1800447E0
0x1800447db  or      eax, 80010000h
0x1800447e0  mov     ebx, eax
0x1800447e2  mov     [rsp+68h+var_38], eax
0x1800447e6  test    eax, eax
0x1800447e8  jns     short loc_180044822
0x1800447ea  mov     rdi, [rsp+68h+arg_0]
0x1800447ef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800447f6  jb      short loc_18004481B
0x1800447f8  mov     edx, 35h ; '5'
0x1800447fd  mov     dword ptr [rsp+68h+var_48], eax
0x180044801  mov     r9, rdi
0x180044804  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x18004480b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044812  mov     rcx, [rcx+10h]
0x180044816  call    WPP_SF_qd
0x18004481b  mov     rsi, [rsp+68h+arg_8]
0x180044820  jmp     short loc_18004486B
0x180044822  mov     rdi, [rsp+68h+arg_0]
0x180044827  mov     rsi, [rsp+68h+arg_8]
0x18004482c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180044833  movdqu  xmmword ptr [rdi+10h], xmm0
0x180044838  mov     eax, 8000FFFFh
0x18004483d  mov     ebx, eax
0x18004483f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044846  jb      short loc_18004486B
0x180044848  mov     edx, 36h ; '6'
0x18004484d  mov     dword ptr [rsp+68h+var_48], eax
0x180044851  mov     rcx, cs:WPP_GLOBAL_Control
0x180044858  mov     r9, rdi
0x18004485b  lea     r8, WPP_9ae5c58d2aea3fa67d5d3545f4fbea04_Traceguids
0x180044862  mov     rcx, [rcx+10h]
0x180044866  call    WPP_SF_qd
0x18004486b  test    ebx, ebx
0x18004486d  jns     short loc_18004487F
0x18004486f  cmp     cs:byte_18009D825, 1
0x180044876  jb      short loc_1800448AC
0x180044878  mov     edx, 37h ; '7'
0x18004487d  jmp     short loc_18004488D
0x18004487f  cmp     cs:byte_18009D825, 8
0x180044886  jb      short loc_1800448AC
0x180044888  mov     edx, 38h ; '8'
0x18004488d  mov     [rsp+68h+var_40], rsi
0x180044892  mov     rcx, cs:WPP_GLOBAL_Control
0x180044899  mov     dword ptr [rsp+68h+var_48], ebx
0x18004489d  mov     r9, rdi
0x1800448a0  mov     rcx, [rcx+0D8h]
0x1800448a7  call    WPP_SF_qDq
0x1800448ac  mov     eax, ebx
0x1800448ae  add     rsp, 50h
0x1800448b2  pop     rdi
0x1800448b3  pop     rsi
0x1800448b4  pop     rbx
0x1800448b5  retn
```
