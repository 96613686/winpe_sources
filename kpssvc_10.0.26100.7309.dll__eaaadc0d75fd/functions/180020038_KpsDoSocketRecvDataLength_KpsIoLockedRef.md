# KpsDoSocketRecvDataLength(KpsIoLockedRef &)

- ea: `0x180020038`
- end: `0x1800202c8`
- name: `?KpsDoSocketRecvDataLength@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `656`
- prototype: `void __fastcall(struct _KPS_IO **this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800223fc`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x180020038`
- `0x180022d38`
- `0x180024be0`
- `0x180026a08`
- `0x180026d9c`
- `0x18002cc3c`
- `0x1800300f4`

## import_xrefs

- `WS2_32!WSARecv` at `0x1800201a3`
- `WS2_32!WSARecv` at `0x1800201a3`
- `WS2_32!__imp_WSAGetLastError` at `0x1800201b4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800201dd`
- `WS2_32!__imp_WSAGetLastError` at `0x1800201b4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800201dd`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180020147`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180020147`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800201d1`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800201d1`
- `ntdll!RtlLeaveCriticalSection` at `0x180020263`
- `ntdll!RtlLeaveCriticalSection` at `0x180020263`

## string_xrefs

- `0x1800200f5`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x180020201`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoSocketRecvDataLength(struct _KPS_IO **this)
{
  unsigned int Error; // esi
  struct _KPS_IO *v3; // rcx
  _QWORD *v4; // rcx
  struct _KPS_IO *v5; // rbx
  int lpOverlappeda; // [rsp+28h] [rbp-30h]
  LPWSAOVERLAPPED lpOverlapped; // [rsp+28h] [rbp-30h]
  struct _WSABUF Buffers; // [rsp+40h] [rbp-18h] BYREF
  DWORD Flags; // [rsp+60h] [rbp+8h] BYREF

  Error = 0;
  Flags = 0;
  Buffers = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *this);
  if ( !KpsServiceReady() )
    goto LABEL_22;
  *((_DWORD *)*this + 67) = 4;
  *((_DWORD *)*this + 66) = 0;
  *((_QWORD *)*this + 32) = KpsAllocMem(*((unsigned int *)*this + 67));
  v3 = *this;
  if ( *((_QWORD *)*this + 32) )
  {
    Buffers.len = *((_DWORD *)v3 + 67);
    Buffers.buf = (CHAR *)*((_QWORD *)v3 + 32);
    *((_DWORD *)v3 + 8) = 9;
    StartThreadpoolIo(*((PTP_IO *)*this + 28));
    if ( *this && _InterlockedIncrement64((volatile signed __int64 *)*this + 43) <= 1 )
      __fastfail(0xEu);
    if ( WSARecv(*((_QWORD *)*this + 27), &Buffers, 1u, 0, &Flags, (LPWSAOVERLAPPED)*this, 0) != -1
      || WSAGetLastError() == 997 )
    {
      v5 = *this;
      KpsStartTimeoutTimer(*this);
      *((_DWORD *)v5 + 84) = 1;
      if ( *this )
      {
        if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this) )
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)*this + 288));
        *this = 0;
      }
    }
    else
    {
      CancelThreadpoolIo(*((PTP_IO *)*this + 28));
      Error = WSAGetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(lpOverlapped) = 1508;
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
          Error,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
          lpOverlapped);
      }
      KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this);
    }
    goto LABEL_22;
  }
  Error = 8;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    lpOverlappeda = 1483;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      8,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      lpOverlappeda);
LABEL_22:
    v4 = WPP_GLOBAL_Control;
  }
  if ( *this )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)this);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_D(v4[2], 69, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, Error);
}

```

## disassembly

```asm
0x180020038  mov     rax, rsp
0x18002003b  mov     [rax+10h], rbx
0x18002003f  mov     [rax+18h], rsi
0x180020043  mov     [rax+20h], rdi
0x180020047  push    r14
0x180020049  sub     rsp, 50h
0x18002004d  xor     esi, esi
0x18002004f  xorps   xmm0, xmm0
0x180020052  and     [rax+8], esi
0x180020055  mov     rdi, rcx
0x180020058  movups  xmmword ptr [rax-18h], xmm0
0x18002005c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020063  lea     r14, WPP_GLOBAL_Control
0x18002006a  cmp     rcx, r14
0x18002006d  jz      short loc_18002008B
0x18002006f  test    byte ptr [rcx+1Ch], 20h
0x180020073  jz      short loc_18002008B
0x180020075  mov     r9, [rdi]
0x180020078  lea     edx, [rsi+42h]
0x18002007b  mov     rcx, [rcx+10h]
0x18002007f  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180020086  call    WPP_SF_q
0x18002008b  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x180020090  test    al, al
0x180020092  jz      loc_180020272
0x180020098  mov     rax, [rdi]
0x18002009b  mov     dword ptr [rax+10Ch], 4
0x1800200a5  mov     rax, [rdi]
0x1800200a8  and     [rax+108h], esi
0x1800200ae  mov     rax, [rdi]
0x1800200b1  mov     ecx, [rax+10Ch]; unsigned __int64
0x1800200b7  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x1800200bc  mov     rcx, [rdi]
0x1800200bf  mov     [rcx+100h], rax
0x1800200c6  mov     rcx, [rdi]
0x1800200c9  cmp     [rcx+100h], rsi
0x1800200d0  jnz     short loc_180020120
0x1800200d2  mov     esi, 8
0x1800200d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200de  cmp     rcx, r14
0x1800200e1  jz      loc_180020279
0x1800200e7  test    byte ptr [rcx+1Ch], 1
0x1800200eb  jz      loc_180020279
0x1800200f1  mov     rcx, [rcx+10h]
0x1800200f5  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x1800200fc  lea     edx, [rsi+3Bh]
0x1800200ff  mov     dword ptr [rsp+58h+lpOverlapped], 5CBh
0x180020107  mov     r9d, esi
0x18002010a  mov     [rsp+58h+lpFlags], rax
0x18002010f  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180020116  call    WPP_SF_Dsd
0x18002011b  jmp     loc_180020272
0x180020120  mov     eax, [rcx+10Ch]
0x180020126  mov     [rsp+58h+Buffers.len], eax
0x18002012a  mov     rax, [rcx+100h]
0x180020131  mov     [rsp+58h+Buffers.buf], rax
0x180020136  mov     dword ptr [rcx+20h], 9
0x18002013d  mov     rcx, [rdi]
0x180020140  mov     rcx, [rcx+0E0h]; pio
0x180020147  call    cs:__imp_StartThreadpoolIo
0x18002014e  nop     dword ptr [rax+rax+00h]
0x180020153  mov     rcx, [rdi]
0x180020156  test    rcx, rcx
0x180020159  jz      short loc_180020179
0x18002015b  mov     eax, 1
0x180020160  lock xadd [rcx+158h], rax
0x180020169  inc     rax
0x18002016c  cmp     rax, 1
0x180020170  jg      short loc_180020179
0x180020172  mov     ecx, 0Eh
0x180020177  int     29h; Win8: RtlFailFast(ecx)
0x180020179  mov     rax, [rdi]
0x18002017c  lea     rcx, [rsp+58h+Flags]
0x180020181  and     [rsp+58h+var_28], rsi
0x180020186  lea     rdx, [rsp+58h+Buffers]; lpBuffers
0x18002018b  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18002018e  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x180020193  mov     [rsp+58h+lpFlags], rcx; lpFlags
0x180020198  mov     rcx, [rax+0D8h]; s
0x18002019f  lea     r8d, [r9+1]; dwBufferCount
0x1800201a3  call    cs:__imp_WSARecv
0x1800201aa  nop     dword ptr [rax+rax+00h]
0x1800201af  cmp     eax, 0FFFFFFFFh
0x1800201b2  jnz     short loc_180020233
0x1800201b4  call    cs:__imp_WSAGetLastError
0x1800201bb  nop     dword ptr [rax+rax+00h]
0x1800201c0  cmp     eax, 3E5h
0x1800201c5  jz      short loc_180020233
0x1800201c7  mov     rcx, [rdi]
0x1800201ca  mov     rcx, [rcx+0E0h]; pio
0x1800201d1  call    cs:__imp_CancelThreadpoolIo
0x1800201d8  nop     dword ptr [rax+rax+00h]
0x1800201dd  call    cs:__imp_WSAGetLastError
0x1800201e4  nop     dword ptr [rax+rax+00h]
0x1800201e9  mov     esi, eax
0x1800201eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201f2  cmp     rcx, r14
0x1800201f5  jz      short loc_180020229
0x1800201f7  test    byte ptr [rcx+1Ch], 1
0x1800201fb  jz      short loc_180020229
0x1800201fd  mov     rcx, [rcx+10h]
0x180020201  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180020208  mov     edx, 44h ; 'D'
0x18002020d  mov     dword ptr [rsp+58h+lpOverlapped], 5E4h
0x180020215  mov     r9d, esi
0x180020218  mov     [rsp+58h+lpFlags], rax
0x18002021d  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180020224  call    WPP_SF_Dsd
0x180020229  mov     rcx, rdi; this
0x18002022c  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180020231  jmp     short loc_180020272
0x180020233  mov     rbx, [rdi]
0x180020236  mov     rcx, rbx; struct _KPS_IO *
0x180020239  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18002023e  mov     dword ptr [rbx+150h], 1
0x180020248  cmp     [rdi], rsi
0x18002024b  jz      short loc_180020272
0x18002024d  mov     rcx, rdi; this
0x180020250  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x180020255  test    al, al
0x180020257  jnz     short loc_18002026F
0x180020259  mov     rcx, [rdi]
0x18002025c  add     rcx, 120h; CriticalSection
0x180020263  call    cs:__imp_RtlLeaveCriticalSection
0x18002026a  nop     dword ptr [rax+rax+00h]
0x18002026f  and     [rdi], rsi
0x180020272  mov     rcx, cs:WPP_GLOBAL_Control
0x180020279  cmp     qword ptr [rdi], 0
0x18002027d  jz      short loc_18002028E
0x18002027f  mov     rcx, rdi; this
0x180020282  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x180020287  mov     rcx, cs:WPP_GLOBAL_Control
0x18002028e  cmp     rcx, r14
0x180020291  jz      short loc_1800202B1
0x180020293  test    byte ptr [rcx+1Ch], 20h
0x180020297  jz      short loc_1800202B1
0x180020299  mov     rcx, [rcx+10h]
0x18002029d  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800202a4  mov     edx, 45h ; 'E'
0x1800202a9  mov     r9d, esi
0x1800202ac  call    WPP_SF_D
0x1800202b1  mov     rbx, [rsp+58h+arg_8]
0x1800202b6  mov     rsi, [rsp+58h+arg_10]
0x1800202bb  mov     rdi, [rsp+58h+arg_18]
0x1800202c0  add     rsp, 50h
0x1800202c4  pop     r14
0x1800202c6  retn
```
