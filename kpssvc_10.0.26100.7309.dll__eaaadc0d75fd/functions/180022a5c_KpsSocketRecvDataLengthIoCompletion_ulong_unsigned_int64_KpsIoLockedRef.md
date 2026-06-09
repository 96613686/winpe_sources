# KpsSocketRecvDataLengthIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x180022a5c`
- end: `0x180022d30`
- name: `?KpsSocketRecvDataLengthIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
- size: `724`
- prototype: `void __fastcall(unsigned int, unsigned __int64, struct KpsIoLockedRef *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800225d0`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001fd08`
- `0x180022a5c`
- `0x180022d38`
- `0x180024be0`
- `0x18002698c`
- `0x180026a08`
- `0x180026de0`

## import_xrefs

- `WS2_32!WSARecv` at `0x180022bfb`
- `WS2_32!WSARecv` at `0x180022bfb`
- `WS2_32!__imp_WSAGetLastError` at `0x180022c0c`
- `WS2_32!__imp_WSAGetLastError` at `0x180022c35`
- `WS2_32!__imp_WSAGetLastError` at `0x180022c0c`
- `WS2_32!__imp_WSAGetLastError` at `0x180022c35`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180022b9f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180022b9f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180022c29`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180022c29`
- `ntdll!RtlLeaveCriticalSection` at `0x180022cbb`
- `ntdll!RtlLeaveCriticalSection` at `0x180022cbb`

## string_xrefs

- `0x180022acc`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x180022c59`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsSocketRecvDataLengthIoCompletion(unsigned int a1, unsigned __int64 a2, struct KpsIoLockedRef *a3)
{
  unsigned int Error; // ebp
  _BYTE *v7; // rcx
  __int64 v8; // rdx
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rbx
  LPWSAOVERLAPPED lpOverlapped; // [rsp+28h] [rbp-40h]
  LPWSAOVERLAPPED lpOverlappeda; // [rsp+28h] [rbp-40h]
  struct _WSABUF Buffers; // [rsp+40h] [rbp-28h] BYREF
  DWORD Flags; // [rsp+70h] [rbp+8h] BYREF

  Error = 0;
  Flags = 0;
  Buffers = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, a3, *(_QWORD *)a3, a1, a2);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v8 = *(_QWORD *)a3;
    v9 = *(_DWORD *)(*(_QWORD *)a3 + 264LL);
    if ( a2 >= (unsigned int)(*(_DWORD *)(*(_QWORD *)a3 + 268LL) - v9) )
    {
      *(_DWORD *)(v8 + 264) = *(_DWORD *)(*(_QWORD *)a3 + 268LL);
      KpsDoSocketRecvData(a3);
    }
    else if ( a2 )
    {
      *(_DWORD *)(v8 + 264) = v9 + a2;
      v10 = *(_QWORD *)a3;
      Buffers.len = *(_DWORD *)(*(_QWORD *)a3 + 268LL) - *(_DWORD *)(*(_QWORD *)a3 + 264LL);
      Buffers.buf = (CHAR *)(*(_QWORD *)(v10 + 256) + *(unsigned int *)(v10 + 264));
      *(_DWORD *)(v10 + 32) = 9;
      StartThreadpoolIo(*(PTP_IO *)(*(_QWORD *)a3 + 224LL));
      if ( *(_QWORD *)a3 && _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)a3 + 344LL)) <= 1 )
        __fastfail(0xEu);
      if ( WSARecv(*(_QWORD *)(*(_QWORD *)a3 + 216LL), &Buffers, 1u, 0, &Flags, *(LPWSAOVERLAPPED *)a3, 0) != -1
        || WSAGetLastError() == 997 )
      {
        v11 = *(_QWORD *)a3;
        KpsStartTimeoutTimer(*(struct _KPS_IO **)a3);
        *(_DWORD *)(v11 + 336) = 1;
        if ( *(_QWORD *)a3 )
        {
          if ( !KpsIoLockedRef::RemoveRef(a3) )
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)a3 + 288LL));
          *(_QWORD *)a3 = 0;
        }
      }
      else
      {
        CancelThreadpoolIo(*(PTP_IO *)(*(_QWORD *)a3 + 224LL));
        Error = WSAGetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(lpOverlappeda) = 2332;
          WPP_SF_Dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            127,
            (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
            Error,
            (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
            lpOverlappeda);
        }
        KpsIoLockedRef::RemoveRef(a3);
      }
    }
    else
    {
      Error = 707;
      if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || (v7[28] & 1) == 0 )
        goto LABEL_29;
      WPP_SF_DILL(*((_QWORD *)v7 + 2), 126);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 1) != 0 )
  {
    LODWORD(lpOverlapped) = 2289;
    WPP_SF_Dsd(
      *((_QWORD *)v7 + 2),
      125,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      a1,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      lpOverlapped);
    v7 = WPP_GLOBAL_Control;
  }
  Error = a1;
LABEL_29:
  if ( *(_QWORD *)a3 )
  {
    KpsDoHttpCancelRequest(a3);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)v7 + 2), 128, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, Error);
}

```

## disassembly

```asm
0x180022a5c  mov     rax, rsp
0x180022a5f  mov     [rax+10h], rbx
0x180022a63  mov     [rax+18h], rbp
0x180022a67  push    rsi
0x180022a68  push    rdi
0x180022a69  push    r15
0x180022a6b  sub     rsp, 50h
0x180022a6f  xor     ebp, ebp
0x180022a71  xorps   xmm0, xmm0
0x180022a74  and     [rax+8], ebp
0x180022a77  mov     rdi, r8
0x180022a7a  movups  xmmword ptr [rax-28h], xmm0
0x180022a7e  mov     rsi, rdx
0x180022a81  mov     ebx, ecx
0x180022a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a8a  lea     r15, WPP_GLOBAL_Control
0x180022a91  cmp     rcx, r15
0x180022a94  jz      short loc_180022AB9
0x180022a96  test    byte ptr [rcx+1Ch], 20h
0x180022a9a  jz      short loc_180022AB9
0x180022a9c  mov     r9, [r8]
0x180022a9f  lea     edx, [rbp+7Ch]
0x180022aa2  mov     rcx, [rcx+10h]
0x180022aa6  mov     [rax-40h], rsi
0x180022aaa  mov     [rax-48h], ebx
0x180022aad  call    WPP_SF_qDI
0x180022ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ab9  test    ebx, ebx
0x180022abb  jz      short loc_180022B02
0x180022abd  cmp     rcx, r15
0x180022ac0  jz      short loc_180022AFB
0x180022ac2  test    byte ptr [rcx+1Ch], 1
0x180022ac6  jz      short loc_180022AFB
0x180022ac8  mov     rcx, [rcx+10h]
0x180022acc  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180022ad3  mov     edx, 7Dh ; '}'
0x180022ad8  mov     dword ptr [rsp+68h+lpOverlapped], 8F1h
0x180022ae0  mov     r9d, ebx
0x180022ae3  mov     [rsp+68h+lpFlags], rax
0x180022ae8  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022aef  call    WPP_SF_Dsd
0x180022af4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022afb  mov     ebp, ebx
0x180022afd  jmp     loc_180022CE2
0x180022b02  mov     rdx, [rdi]
0x180022b05  mov     r8d, [rdx+10Ch]
0x180022b0c  mov     eax, r8d
0x180022b0f  mov     r9d, [rdx+108h]
0x180022b16  sub     eax, r9d
0x180022b19  cmp     rsi, rax
0x180022b1c  jnb     loc_180022CCC
0x180022b22  test    rsi, rsi
0x180022b25  jnz     short loc_180022B5F
0x180022b27  mov     ebp, 2C3h
0x180022b2c  cmp     rcx, r15
0x180022b2f  jz      loc_180022CE2
0x180022b35  test    byte ptr [rcx+1Ch], 1
0x180022b39  jz      loc_180022CE2
0x180022b3f  mov     rcx, [rcx+10h]
0x180022b43  lea     edx, [rsi+7Eh]
0x180022b46  mov     dword ptr [rsp+68h+var_38], r8d
0x180022b4b  mov     dword ptr [rsp+68h+lpOverlapped], r9d
0x180022b50  mov     [rsp+68h+lpFlags], rsi
0x180022b55  call    WPP_SF_DILL
0x180022b5a  jmp     loc_180022CDB
0x180022b5f  lea     eax, [r9+rsi]
0x180022b63  mov     [rdx+108h], eax
0x180022b69  mov     rcx, [rdi]
0x180022b6c  mov     eax, [rcx+10Ch]
0x180022b72  sub     eax, [rcx+108h]
0x180022b78  mov     [rsp+68h+Buffers.len], eax
0x180022b7c  mov     eax, [rcx+108h]
0x180022b82  add     rax, [rcx+100h]
0x180022b89  mov     [rsp+68h+Buffers.buf], rax
0x180022b8e  mov     dword ptr [rcx+20h], 9
0x180022b95  mov     rcx, [rdi]
0x180022b98  mov     rcx, [rcx+0E0h]; pio
0x180022b9f  call    cs:__imp_StartThreadpoolIo
0x180022ba6  nop     dword ptr [rax+rax+00h]
0x180022bab  mov     rcx, [rdi]
0x180022bae  test    rcx, rcx
0x180022bb1  jz      short loc_180022BD1
0x180022bb3  mov     eax, 1
0x180022bb8  lock xadd [rcx+158h], rax
0x180022bc1  inc     rax
0x180022bc4  cmp     rax, 1
0x180022bc8  jg      short loc_180022BD1
0x180022bca  mov     ecx, 0Eh
0x180022bcf  int     29h; Win8: RtlFailFast(ecx)
0x180022bd1  mov     rax, [rdi]
0x180022bd4  lea     rcx, [rsp+68h+Flags]
0x180022bd9  and     [rsp+68h+var_38], rbp
0x180022bde  lea     rdx, [rsp+68h+Buffers]; lpBuffers
0x180022be3  xor     r9d, r9d; lpNumberOfBytesRecvd
0x180022be6  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x180022beb  mov     [rsp+68h+lpFlags], rcx; lpFlags
0x180022bf0  mov     rcx, [rax+0D8h]; s
0x180022bf7  lea     r8d, [r9+1]; dwBufferCount
0x180022bfb  call    cs:__imp_WSARecv
0x180022c02  nop     dword ptr [rax+rax+00h]
0x180022c07  cmp     eax, 0FFFFFFFFh
0x180022c0a  jnz     short loc_180022C8B
0x180022c0c  call    cs:__imp_WSAGetLastError
0x180022c13  nop     dword ptr [rax+rax+00h]
0x180022c18  cmp     eax, 3E5h
0x180022c1d  jz      short loc_180022C8B
0x180022c1f  mov     rcx, [rdi]
0x180022c22  mov     rcx, [rcx+0E0h]; pio
0x180022c29  call    cs:__imp_CancelThreadpoolIo
0x180022c30  nop     dword ptr [rax+rax+00h]
0x180022c35  call    cs:__imp_WSAGetLastError
0x180022c3c  nop     dword ptr [rax+rax+00h]
0x180022c41  mov     ebp, eax
0x180022c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c4a  cmp     rcx, r15
0x180022c4d  jz      short loc_180022C81
0x180022c4f  test    byte ptr [rcx+1Ch], 1
0x180022c53  jz      short loc_180022C81
0x180022c55  mov     rcx, [rcx+10h]
0x180022c59  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180022c60  mov     edx, 7Fh
0x180022c65  mov     dword ptr [rsp+68h+lpOverlapped], 91Ch
0x180022c6d  mov     r9d, ebp
0x180022c70  mov     [rsp+68h+lpFlags], rax
0x180022c75  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022c7c  call    WPP_SF_Dsd
0x180022c81  mov     rcx, rdi; this
0x180022c84  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180022c89  jmp     short loc_180022CDB
0x180022c8b  mov     rbx, [rdi]
0x180022c8e  mov     rcx, rbx; struct _KPS_IO *
0x180022c91  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x180022c96  mov     dword ptr [rbx+150h], 1
0x180022ca0  cmp     [rdi], rbp
0x180022ca3  jz      short loc_180022CDB
0x180022ca5  mov     rcx, rdi; this
0x180022ca8  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180022cad  test    al, al
0x180022caf  jnz     short loc_180022CC7
0x180022cb1  mov     rcx, [rdi]
0x180022cb4  add     rcx, 120h; CriticalSection
0x180022cbb  call    cs:__imp_RtlLeaveCriticalSection
0x180022cc2  nop     dword ptr [rax+rax+00h]
0x180022cc7  and     [rdi], rbp
0x180022cca  jmp     short loc_180022CDB
0x180022ccc  mov     rcx, rdi; this
0x180022ccf  mov     [rdx+108h], r8d
0x180022cd6  call    ?KpsDoSocketRecvData@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoSocketRecvData(KpsIoLockedRef &)
0x180022cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ce2  cmp     qword ptr [rdi], 0
0x180022ce6  jz      short loc_180022CF7
0x180022ce8  mov     rcx, rdi; this
0x180022ceb  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x180022cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cf7  cmp     rcx, r15
0x180022cfa  jz      short loc_180022D1A
0x180022cfc  test    byte ptr [rcx+1Ch], 20h
0x180022d00  jz      short loc_180022D1A
0x180022d02  mov     rcx, [rcx+10h]
0x180022d06  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022d0d  mov     edx, 80h
0x180022d12  mov     r9d, ebp
0x180022d15  call    WPP_SF_D
0x180022d1a  lea     r11, [rsp+68h+var_18]
0x180022d1f  mov     rbx, [r11+28h]
0x180022d23  mov     rbp, [r11+30h]
0x180022d27  mov     rsp, r11
0x180022d2a  pop     r15
0x180022d2c  pop     rdi
0x180022d2d  pop     rsi
0x180022d2e  retn
```
