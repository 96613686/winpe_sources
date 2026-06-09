# KpsSocketRecvDataIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x180022708`
- end: `0x180022a54`
- name: `?KpsSocketRecvDataIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
- size: `844`
- prototype: `void __fastcall(unsigned int, unsigned __int64, struct _KPS_IO **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800225d0`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001f048`
- `0x18001f390`
- `0x180022708`
- `0x180022d38`
- `0x180024be0`
- `0x18002698c`
- `0x180026a08`
- `0x180026de0`
- `0x18002a42c`
- `0x18002fe08`

## import_xrefs

- `WS2_32!WSARecv` at `0x1800228ab`
- `WS2_32!WSARecv` at `0x1800228ab`
- `WS2_32!__imp_WSAGetLastError` at `0x1800228c0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800228e9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800228c0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800228e9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002284f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18002284f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800228dd`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800228dd`
- `ntdll!RtlLeaveCriticalSection` at `0x180022976`
- `ntdll!RtlLeaveCriticalSection` at `0x180022976`

## string_xrefs

- `0x18002277a`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18002290d`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x1800229cd`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsSocketRecvDataIoCompletion(unsigned int a1, unsigned __int64 a2, struct _KPS_IO **a3)
{
  unsigned int Error; // esi
  _BYTE *v7; // rcx
  struct _KPS_IO *v8; // rdx
  int v9; // r9d
  struct _KPS_IO *v10; // rcx
  struct _KPS_IO *v11; // rbx
  unsigned __int16 v12; // dx
  char *v13; // r8
  char *v14; // r9
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
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, a3, *a3, a1, a2);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v8 = *a3;
    v9 = *((_DWORD *)*a3 + 66);
    if ( a2 >= (unsigned int)(*((_DWORD *)*a3 + 67) - v9) )
    {
      *((_DWORD *)v8 + 66) = *((_DWORD *)*a3 + 67);
      Error = KpsPackProxyResponse(*a3);
      if ( Error == 1935 )
      {
        KpsPerfUpdate(4u);
        KpsDoHttpSendResponse((struct KpsIoLockedRef *)a3, v12, v13, v14);
      }
      else if ( Error )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_35;
        LODWORD(lpOverlapped) = 2445;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          133,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          Error,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          lpOverlapped);
      }
      else
      {
        KpsDoHttpSendPostResponse((struct KpsIoLockedRef *)a3);
      }
    }
    else if ( a2 )
    {
      *((_DWORD *)v8 + 66) = v9 + a2;
      v10 = *a3;
      Buffers.len = *((_DWORD *)*a3 + 67) - *((_DWORD *)*a3 + 66);
      Buffers.buf = (CHAR *)(*((_QWORD *)v10 + 32) + *((unsigned int *)v10 + 66));
      *((_DWORD *)v10 + 8) = 10;
      StartThreadpoolIo(*((PTP_IO *)*a3 + 28));
      if ( *a3 && _InterlockedIncrement64((volatile signed __int64 *)*a3 + 43) <= 1 )
        __fastfail(0xEu);
      if ( WSARecv(*((_QWORD *)*a3 + 27), &Buffers, 1u, 0, &Flags, (LPWSAOVERLAPPED)*a3, 0) != -1
        || WSAGetLastError() == 997 )
      {
        v11 = *a3;
        KpsStartTimeoutTimer(*a3);
        *((_DWORD *)v11 + 84) = 1;
        if ( *a3 )
        {
          if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3) )
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)*a3 + 288));
          *a3 = 0;
        }
      }
      else
      {
        CancelThreadpoolIo(*((PTP_IO *)*a3 + 28));
        Error = WSAGetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(lpOverlappeda) = 2419;
          WPP_SF_Dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            132,
            (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
            Error,
            (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
            lpOverlappeda);
        }
        KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)a3);
      }
    }
    else
    {
      Error = 707;
      if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || (v7[28] & 1) == 0 )
        goto LABEL_35;
      WPP_SF_DILL(*((_QWORD *)v7 + 2), 131);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 1) != 0 )
  {
    LODWORD(lpOverlapped) = 2376;
    WPP_SF_Dsd(
      *((_QWORD *)v7 + 2),
      130,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      a1,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      lpOverlapped);
    v7 = WPP_GLOBAL_Control;
  }
  Error = a1;
LABEL_35:
  if ( *a3 )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)a3);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)v7 + 2), 134, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, Error);
}

```

## disassembly

```asm
0x180022708  mov     rax, rsp
0x18002270b  mov     [rax+10h], rbx
0x18002270f  mov     [rax+18h], rbp
0x180022713  push    rsi
0x180022714  push    rdi
0x180022715  push    r15
0x180022717  sub     rsp, 50h
0x18002271b  xor     esi, esi
0x18002271d  xorps   xmm0, xmm0
0x180022720  and     [rax+8], esi
0x180022723  mov     rdi, r8
0x180022726  movups  xmmword ptr [rax-28h], xmm0
0x18002272a  mov     rbp, rdx
0x18002272d  mov     ebx, ecx
0x18002272f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022736  lea     r15, WPP_GLOBAL_Control
0x18002273d  cmp     rcx, r15
0x180022740  jz      short loc_180022767
0x180022742  test    byte ptr [rcx+1Ch], 20h
0x180022746  jz      short loc_180022767
0x180022748  mov     r9, [r8]
0x18002274b  mov     edx, 81h
0x180022750  mov     rcx, [rcx+10h]
0x180022754  mov     [rax-40h], rbp
0x180022758  mov     [rax-48h], ebx
0x18002275b  call    WPP_SF_qDI
0x180022760  mov     rcx, cs:WPP_GLOBAL_Control
0x180022767  test    ebx, ebx
0x180022769  jz      short loc_1800227B0
0x18002276b  cmp     rcx, r15
0x18002276e  jz      short loc_1800227A9
0x180022770  test    byte ptr [rcx+1Ch], 1
0x180022774  jz      short loc_1800227A9
0x180022776  mov     rcx, [rcx+10h]
0x18002277a  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180022781  mov     edx, 82h
0x180022786  mov     dword ptr [rsp+68h+lpOverlapped], 948h
0x18002278e  mov     r9d, ebx
0x180022791  mov     [rsp+68h+lpFlags], rax
0x180022796  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18002279d  call    WPP_SF_Dsd
0x1800227a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227a9  mov     esi, ebx
0x1800227ab  jmp     loc_180022A06
0x1800227b0  mov     rdx, [rdi]
0x1800227b3  mov     r8d, [rdx+10Ch]
0x1800227ba  mov     eax, r8d
0x1800227bd  mov     r9d, [rdx+108h]
0x1800227c4  sub     eax, r9d
0x1800227c7  cmp     rbp, rax
0x1800227ca  jnb     loc_180022987
0x1800227d0  test    rbp, rbp
0x1800227d3  jnz     short loc_18002280F
0x1800227d5  mov     esi, 2C3h
0x1800227da  cmp     rcx, r15
0x1800227dd  jz      loc_180022A06
0x1800227e3  test    byte ptr [rcx+1Ch], 1
0x1800227e7  jz      loc_180022A06
0x1800227ed  mov     rcx, [rcx+10h]
0x1800227f1  mov     edx, 83h
0x1800227f6  mov     dword ptr [rsp+68h+var_38], r8d
0x1800227fb  mov     dword ptr [rsp+68h+lpOverlapped], r9d
0x180022800  mov     [rsp+68h+lpFlags], rbp
0x180022805  call    WPP_SF_DILL
0x18002280a  jmp     loc_1800229FF
0x18002280f  lea     eax, [r9+rbp]
0x180022813  mov     [rdx+108h], eax
0x180022819  mov     rcx, [rdi]
0x18002281c  mov     eax, [rcx+10Ch]
0x180022822  sub     eax, [rcx+108h]
0x180022828  mov     [rsp+68h+Buffers.len], eax
0x18002282c  mov     eax, [rcx+108h]
0x180022832  add     rax, [rcx+100h]
0x180022839  mov     [rsp+68h+Buffers.buf], rax
0x18002283e  mov     dword ptr [rcx+20h], 0Ah
0x180022845  mov     rcx, [rdi]
0x180022848  mov     rcx, [rcx+0E0h]; pio
0x18002284f  call    cs:__imp_StartThreadpoolIo
0x180022856  nop     dword ptr [rax+rax+00h]
0x18002285b  mov     rcx, [rdi]
0x18002285e  test    rcx, rcx
0x180022861  jz      short loc_180022881
0x180022863  mov     eax, 1
0x180022868  lock xadd [rcx+158h], rax
0x180022871  inc     rax
0x180022874  cmp     rax, 1
0x180022878  jg      short loc_180022881
0x18002287a  mov     ecx, 0Eh
0x18002287f  int     29h; Win8: RtlFailFast(ecx)
0x180022881  mov     rax, [rdi]
0x180022884  lea     rcx, [rsp+68h+Flags]
0x180022889  and     [rsp+68h+var_38], rsi
0x18002288e  lea     rdx, [rsp+68h+Buffers]; lpBuffers
0x180022893  xor     r9d, r9d; lpNumberOfBytesRecvd
0x180022896  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18002289b  mov     [rsp+68h+lpFlags], rcx; lpFlags
0x1800228a0  mov     rcx, [rax+0D8h]; s
0x1800228a7  lea     r8d, [r9+1]; dwBufferCount
0x1800228ab  call    cs:__imp_WSARecv
0x1800228b2  nop     dword ptr [rax+rax+00h]
0x1800228b7  cmp     eax, 0FFFFFFFFh
0x1800228ba  jnz     loc_180022942
0x1800228c0  call    cs:__imp_WSAGetLastError
0x1800228c7  nop     dword ptr [rax+rax+00h]
0x1800228cc  cmp     eax, 3E5h
0x1800228d1  jz      short loc_180022942
0x1800228d3  mov     rcx, [rdi]
0x1800228d6  mov     rcx, [rcx+0E0h]; pio
0x1800228dd  call    cs:__imp_CancelThreadpoolIo
0x1800228e4  nop     dword ptr [rax+rax+00h]
0x1800228e9  call    cs:__imp_WSAGetLastError
0x1800228f0  nop     dword ptr [rax+rax+00h]
0x1800228f5  mov     esi, eax
0x1800228f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228fe  cmp     rcx, r15
0x180022901  jz      short loc_180022935
0x180022903  test    byte ptr [rcx+1Ch], 1
0x180022907  jz      short loc_180022935
0x180022909  mov     rcx, [rcx+10h]
0x18002290d  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180022914  mov     edx, 84h
0x180022919  mov     dword ptr [rsp+68h+lpOverlapped], 973h
0x180022921  mov     r9d, esi
0x180022924  mov     [rsp+68h+lpFlags], rax
0x180022929  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022930  call    WPP_SF_Dsd
0x180022935  mov     rcx, rdi; this
0x180022938  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18002293d  jmp     loc_1800229FF
0x180022942  mov     rbx, [rdi]
0x180022945  mov     rcx, rbx; struct _KPS_IO *
0x180022948  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18002294d  mov     dword ptr [rbx+150h], 1
0x180022957  cmp     [rdi], rsi
0x18002295a  jz      loc_1800229FF
0x180022960  mov     rcx, rdi; this
0x180022963  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180022968  test    al, al
0x18002296a  jnz     short loc_180022982
0x18002296c  mov     rcx, [rdi]
0x18002296f  add     rcx, 120h; CriticalSection
0x180022976  call    cs:__imp_RtlLeaveCriticalSection
0x18002297d  nop     dword ptr [rax+rax+00h]
0x180022982  and     [rdi], rsi
0x180022985  jmp     short loc_1800229FF
0x180022987  mov     [rdx+108h], r8d
0x18002298e  mov     rcx, [rdi]; struct _KPS_IO *
0x180022991  call    ?KpsPackProxyResponse@@YAKPEAU_KPS_IO@@@Z; KpsPackProxyResponse(_KPS_IO *)
0x180022996  mov     esi, eax
0x180022998  cmp     eax, 78Fh
0x18002299d  jnz     short loc_1800229B3
0x18002299f  mov     ecx, 4; unsigned int
0x1800229a4  call    ?KpsPerfUpdate@@YAXK@Z; KpsPerfUpdate(ulong)
0x1800229a9  mov     rcx, rdi; this
0x1800229ac  call    ?KpsDoHttpSendResponse@@YAXAEAVKpsIoLockedRef@@GPEAD1@Z; KpsDoHttpSendResponse(KpsIoLockedRef &,ushort,char *,char *)
0x1800229b1  jmp     short loc_1800229FF
0x1800229b3  test    esi, esi
0x1800229b5  jz      short loc_1800229F7
0x1800229b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229be  cmp     rcx, r15
0x1800229c1  jz      short loc_180022A06
0x1800229c3  test    byte ptr [rcx+1Ch], 1
0x1800229c7  jz      short loc_180022A06
0x1800229c9  mov     rcx, [rcx+10h]
0x1800229cd  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x1800229d4  mov     edx, 85h
0x1800229d9  mov     dword ptr [rsp+68h+lpOverlapped], 98Dh
0x1800229e1  mov     r9d, esi
0x1800229e4  mov     [rsp+68h+lpFlags], rax
0x1800229e9  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800229f0  call    WPP_SF_Dsd
0x1800229f5  jmp     short loc_1800229FF
0x1800229f7  mov     rcx, rdi; this
0x1800229fa  call    ?KpsDoHttpSendPostResponse@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpSendPostResponse(KpsIoLockedRef &)
0x1800229ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a06  cmp     qword ptr [rdi], 0
0x180022a0a  jz      short loc_180022A1B
0x180022a0c  mov     rcx, rdi; this
0x180022a0f  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x180022a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a1b  cmp     rcx, r15
0x180022a1e  jz      short loc_180022A3E
0x180022a20  test    byte ptr [rcx+1Ch], 20h
0x180022a24  jz      short loc_180022A3E
0x180022a26  mov     rcx, [rcx+10h]
0x180022a2a  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022a31  mov     edx, 86h
0x180022a36  mov     r9d, esi
0x180022a39  call    WPP_SF_D
0x180022a3e  lea     r11, [rsp+68h+var_18]
0x180022a43  mov     rbx, [r11+28h]
0x180022a47  mov     rbp, [r11+30h]
0x180022a4b  mov     rsp, r11
0x180022a4e  pop     r15
0x180022a50  pop     rdi
0x180022a51  pop     rsi
0x180022a52  retn
```
