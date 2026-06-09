# DnsFwTcpAccept(_DNS_FORWARD_SOCKET *)

- ea: `0x1800445c8`
- end: `0x1800447b5`
- name: `?DnsFwTcpAccept@@YAKPEAU_DNS_FORWARD_SOCKET@@@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct _DNS_FORWARD_SOCKET *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004368c`
- `0x180043eb8`

## callees

- `0x180008b00`
- `0x1800432fc`
- `0x18004345c`
- `0x18004368c`
- `0x1800445c8`
- `0x180046ec0`
- `0x180086b1c`
- `0x180086f24`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180044685`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180044685`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044713`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044713`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800446a9`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800446a9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004472d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18004472d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800446f4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800446f4`

## pseudocode

```c
__int64 __fastcall DnsFwTcpAccept(struct _DNS_FORWARD_SOCKET *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  unsigned int v4; // esi
  struct _DNS_FORWARD_CONTEXT *v5; // r14
  PTP_IO *v6; // r15
  int Error; // eax
  unsigned int v8; // eax
  struct _DNS_FORWARD_CONTEXT *lpMem; // [rsp+58h] [rbp-18h] BYREF
  unsigned int v11; // [rsp+60h] [rbp-10h] BYREF

  lpMem = 0;
  v11 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 22, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, a1);
  if ( !a1 )
  {
    v2 = -2147024809;
    goto LABEL_19;
  }
  v3 = DnsFwCreateContext(a1, &lpMem);
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( (v2 & 0x80000000) == 0 )
  {
    v4 = 0;
    *((_DWORD *)lpMem + 9) = 1;
    v5 = lpMem;
    _InterlockedIncrement((volatile signed __int32 *)lpMem + 8);
    AcquireSRWLockShared((PSRWLOCK)a1 + 4);
    v6 = (PTP_IO *)((char *)a1 + 72);
    if ( *((_QWORD *)a1 + 6) == -1 )
    {
      v2 = 995;
LABEL_15:
      ReleaseSRWLockShared((PSRWLOCK)a1 + 4);
      if ( v5 )
        DnsFwDerefContext(v5);
      if ( v4 )
      {
        CancelThreadpoolIo(*v6);
        DnsFwIoCompletionRoutine(lpMem, v4, v11);
        lpMem = 0;
      }
      goto LABEL_19;
    }
    v2 = 0;
    StartThreadpoolIo(*v6);
    if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, char *, _QWORD, int, int, unsigned int *, char *))g_pfnAcceptEx)(
                          *((_QWORD *)a1 + 6),
                          *(_QWORD *)(*((_QWORD *)v5 + 8) + 48LL),
                          (char *)v5 + 72,
                          0,
                          144,
                          144,
                          &v11,
                          (char *)v5 + 480) )
    {
      Error = WSAGetLastError();
      v4 = Error;
      if ( Error == 997 )
      {
        v4 = 0;
      }
      else if ( Error )
      {
        goto LABEL_15;
      }
    }
    lpMem = 0;
    goto LABEL_15;
  }
LABEL_19:
  if ( lpMem )
  {
    DnsFwDerefContext(lpMem);
    lpMem = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v8 = WX_WIN32_FROM_HR(v2);
    WPP_SF_d(1035, 23, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v8);
  }
  return WX_WIN32_FROM_HR(v2);
}

```

## disassembly

```asm
0x1800445c8  mov     [rsp-28h+arg_8], rbx
0x1800445cd  mov     [rsp-28h+arg_10], rsi
0x1800445d2  push    rbp
0x1800445d3  push    rdi
0x1800445d4  push    r12
0x1800445d6  push    r14
0x1800445d8  push    r15
0x1800445da  mov     rbp, rsp
0x1800445dd  sub     rsp, 70h
0x1800445e1  mov     rax, cs:__security_cookie
0x1800445e8  xor     rax, rsp
0x1800445eb  mov     [rbp+var_8], rax
0x1800445ef  mov     rdi, rcx
0x1800445f2  mov     [rbp+var_1C], 0
0x1800445f9  mov     [rbp+lpMem], 0
0x180044601  mov     [rbp+var_10], 0
0x180044608  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004460f  jz      short loc_18004462A
0x180044611  mov     edx, 16h
0x180044616  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x18004461d  mov     ecx, 40Bh
0x180044622  mov     r9, rdi
0x180044625  call    WPP_SF_q
0x18004462a  test    rdi, rdi
0x18004462d  jnz     short loc_180044640
0x18004462f  mov     ebx, 80070057h
0x180044634  mov     [rbp+var_1C], 20Dh
0x18004463b  jmp     loc_18004474A
0x180044640  lea     rdx, [rbp+lpMem]; struct _DNS_FORWARD_CONTEXT **
0x180044644  mov     rcx, rdi; struct _DNS_FORWARD_SOCKET *
0x180044647  call    ?DnsFwCreateContext@@YAKPEAU_DNS_FORWARD_SOCKET@@PEAPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwCreateContext(_DNS_FORWARD_SOCKET *,_DNS_FORWARD_CONTEXT * *)
0x18004464c  mov     ebx, eax
0x18004464e  test    eax, eax
0x180044650  jle     short loc_18004465B
0x180044652  movzx   ebx, ax
0x180044655  or      ebx, 80070000h
0x18004465b  test    ebx, ebx
0x18004465d  jns     short loc_18004466B
0x18004465f  mov     [rbp+var_1C], 213h
0x180044666  jmp     loc_18004474A
0x18004466b  mov     rax, [rbp+lpMem]
0x18004466f  xor     esi, esi
0x180044671  mov     dword ptr [rax+24h], 1
0x180044678  mov     r14, [rbp+lpMem]
0x18004467c  lock inc dword ptr [r14+20h]
0x180044681  lea     rcx, [rdi+20h]; SRWLock
0x180044685  call    cs:__imp_AcquireSRWLockShared
0x18004468b  cmp     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x180044690  lea     r15, [rdi+48h]
0x180044694  jnz     short loc_1800446A4
0x180044696  mov     ebx, 3E3h
0x18004469b  mov     [rbp+var_1C], 221h
0x1800446a2  jmp     short loc_18004470F
0x1800446a4  mov     rcx, [r15]; pio
0x1800446a7  xor     ebx, ebx
0x1800446a9  call    cs:__imp_StartThreadpoolIo
0x1800446af  mov     rdx, [r14+40h]
0x1800446b3  lea     rax, [r14+1E0h]
0x1800446ba  mov     rcx, [rdi+30h]
0x1800446be  lea     r8, [r14+48h]
0x1800446c2  mov     [rsp+70h+var_38], rax
0x1800446c7  xor     r9d, r9d
0x1800446ca  lea     rax, [rbp+var_10]
0x1800446ce  mov     rdx, [rdx+30h]
0x1800446d2  mov     [rsp+70h+var_40], rax
0x1800446d7  mov     eax, 90h
0x1800446dc  mov     [rsp+70h+var_48], eax
0x1800446e0  mov     [rsp+70h+var_50], eax
0x1800446e4  mov     rax, cs:?g_pfnAcceptEx@@3P6AH_K0PEAXKKKPEAKPEAU_OVERLAPPED@@@ZEA; int (*g_pfnAcceptEx)(unsigned __int64,unsigned __int64,void *,ulong,ulong,ulong,ulong *,_OVERLAPPED *)
0x1800446eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446f0  test    eax, eax
0x1800446f2  jnz     short loc_18004470B
0x1800446f4  call    cs:__imp_WSAGetLastError
0x1800446fa  mov     esi, eax
0x1800446fc  cmp     eax, 3E5h
0x180044701  jnz     short loc_180044707
0x180044703  xor     esi, esi
0x180044705  jmp     short loc_18004470B
0x180044707  test    eax, eax
0x180044709  jnz     short loc_18004470F
0x18004470b  mov     [rbp+lpMem], rbx
0x18004470f  lea     rcx, [rdi+20h]; SRWLock
0x180044713  call    cs:__imp_ReleaseSRWLockShared
0x180044719  test    r14, r14
0x18004471c  jz      short loc_180044726
0x18004471e  mov     rcx, r14; lpMem
0x180044721  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x180044726  test    esi, esi
0x180044728  jz      short loc_18004474A
0x18004472a  mov     rcx, [r15]; pio
0x18004472d  call    cs:__imp_CancelThreadpoolIo
0x180044733  mov     r8d, [rbp+var_10]; unsigned int
0x180044737  mov     edx, esi; unsigned int
0x180044739  mov     rcx, [rbp+lpMem]; lpMem
0x18004473d  call    ?DnsFwIoCompletionRoutine@@YAKPEAU_DNS_FORWARD_CONTEXT@@KK@Z; DnsFwIoCompletionRoutine(_DNS_FORWARD_CONTEXT *,ulong,ulong)
0x180044742  mov     [rbp+lpMem], 0
0x18004474a  mov     rcx, [rbp+lpMem]; lpMem
0x18004474e  test    rcx, rcx
0x180044751  jz      short loc_180044760
0x180044753  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x180044758  mov     [rbp+lpMem], 0
0x180044760  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180044767  jz      short loc_180044789
0x180044769  mov     ecx, ebx
0x18004476b  call    WX_WIN32_FROM_HR
0x180044770  mov     r9d, eax
0x180044773  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x18004477a  mov     edx, 17h
0x18004477f  mov     ecx, 40Bh
0x180044784  call    WPP_SF_d
0x180044789  mov     ecx, ebx
0x18004478b  call    WX_WIN32_FROM_HR
0x180044790  mov     rcx, [rbp+var_8]
0x180044794  xor     rcx, rsp; StackCookie
0x180044797  call    __security_check_cookie
0x18004479c  lea     r11, [rsp+70h+var_s0]
0x1800447a1  mov     rbx, [r11+38h]
0x1800447a5  mov     rsi, [r11+40h]
0x1800447a9  mov     rsp, r11
0x1800447ac  pop     r15
0x1800447ae  pop     r14
0x1800447b0  pop     r12
0x1800447b2  pop     rdi
0x1800447b3  pop     rbp
0x1800447b4  retn
```
