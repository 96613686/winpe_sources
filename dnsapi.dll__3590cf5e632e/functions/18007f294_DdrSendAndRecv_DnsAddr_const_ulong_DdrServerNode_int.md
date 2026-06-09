# DdrSendAndRecv(_DnsAddr const *,ulong,DdrServerNode *,int *)

- ea: `0x18007f294`
- end: `0x18007f554`
- name: `?DdrSendAndRecv@@YAJPEBU_DnsAddr@@KPEAVDdrServerNode@@PEAH@Z`
- size: `704`
- prototype: `__int64 __fastcall(const struct _DnsAddr *, unsigned int, struct DdrServerNode *, int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800b1128`
- `0x1800b21e0`

## callees

- `0x18001f03c`
- `0x18002144c`
- `0x18002a0e0`
- `0x180053404`
- `0x18005bd0c`
- `0x18005e218`
- `0x180062f60`
- `0x18007f294`
- `0x18007f55c`
- `0x18007f67c`
- `0x18008b5f0`
- `0x1800cfadc`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f469`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007f469`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f4b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f4b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007f3ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007f3ca`

## pseudocode

```c
__int64 __fastcall DdrSendAndRecv(const struct _DnsAddr *a1, int a2, struct _LIST_ENTRY *a3, int *a4)
{
  struct _LIST_ENTRY *v4; // r14
  struct _LIST_ENTRY *v5; // rsi
  unsigned int v10; // edi
  signed int v11; // ebx
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  struct _LIST_ENTRY *v15; // rcx
  int v16; // eax
  PVOID pv; // [rsp+48h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-10h] BYREF

  v4 = 0;
  v5 = 0;
  pv = 0;
  lpMem = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF__SOCKADDR_d((_DWORD)a1, 43, (unsigned int)WPP_fa4a0884474b39b1dc1745622c5c399f_Traceguids, (_DWORD)a1, a2);
  if ( !a4 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    goto LABEL_25;
  }
  *a4 = 1;
  if ( !a1 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    goto LABEL_25;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    goto LABEL_25;
  }
  v12 = DdrCreateNetInfo(a1, &lpMem);
  v11 = v12;
  if ( v12 > 0 )
    v11 = (unsigned __int16)v12 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_12;
  *((_DWORD *)lpMem + 38) = a2;
  v13 = Dns_BuildPacketInternal(0, 1, (unsigned int)L"_dns.resolver.arpa", 64, 0, 0x10000000, 0, 0);
  v4 = (struct _LIST_ENTRY *)v13;
  if ( !v13 )
  {
    v11 = -2147024882;
LABEL_12:
    v10 = v11;
    goto LABEL_25;
  }
  AddRefDnsMessage(v13);
  LODWORD(v4[41].Blink) = GetCurrentProcessId();
  v14 = Send_CreateSendBlob(&pv);
  v11 = v14;
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  v5 = (struct _LIST_ENTRY *)pv;
  if ( v11 < 0 )
    goto LABEL_12;
  *((_DWORD *)pv + 122) = v4[41].Blink;
  v5[5].Blink = v4;
  v5[2].Flink = (struct _LIST_ENTRY *)lpMem;
  lpMem = 0;
  v5[10].Blink = (struct _LIST_ENTRY *)0x1000000000000008LL;
  HIDWORD(v5[11].Flink) = 1;
  *a4 = 0;
  v5[29].Blink = (struct _LIST_ENTRY *)DdrQueryCallback;
  v5[29].Flink = a3;
  _InterlockedAdd((volatile signed __int32 *)a3, 1u);
  EnterCriticalSection(&g_csDdrCleanup);
  AddRefSendBlob(v5);
  v15 = off_180111330;
  if ( off_180111330->Flink != &g_DdrQueryCleanupList )
    __fastfail(3u);
  v4 = 0;
  v5[40].Blink = off_180111330;
  v5[40].Flink = &g_DdrQueryCleanupList;
  v15->Flink = v5 + 40;
  off_180111330 = v5 + 40;
  LeaveCriticalSection(&g_csDdrCleanup);
  v16 = Send_AndRecv(v5);
  v11 = v16;
  if ( v16 != 9506 )
  {
    if ( v16 > 0 )
      v11 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_12;
  }
  v11 = 0;
  v10 = 0;
LABEL_25:
  NetInfo_Free(lpMem);
  lpMem = 0;
  DeRefDnsMessage(v4);
  DeRefSendBlob((char *)v5);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 44, WPP_fa4a0884474b39b1dc1745622c5c399f_Traceguids, (unsigned int)v11);
  return v10;
}

```

## disassembly

```asm
0x18007f294  push    rbp
0x18007f296  push    rbx
0x18007f297  push    rsi
0x18007f298  push    rdi
0x18007f299  push    r12
0x18007f29b  push    r14
0x18007f29d  push    r15
0x18007f29f  mov     rbp, rsp
0x18007f2a2  sub     rsp, 60h
0x18007f2a6  mov     rax, cs:__security_cookie
0x18007f2ad  xor     rax, rsp
0x18007f2b0  mov     [rbp+var_8], rax
0x18007f2b4  xor     r14d, r14d
0x18007f2b7  mov     [rbp+var_1C], 0
0x18007f2be  xor     esi, esi
0x18007f2c0  mov     rdi, r9
0x18007f2c3  mov     [rbp+pv], rsi
0x18007f2c7  mov     r12, r8
0x18007f2ca  mov     [rbp+lpMem], rsi
0x18007f2ce  mov     r15d, edx
0x18007f2d1  mov     rbx, rcx
0x18007f2d4  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007f2db  jz      short loc_18007F2F4
0x18007f2dd  lea     edx, [rsi+2Bh]
0x18007f2e0  mov     dword ptr [rsp+60h+var_40], r15d
0x18007f2e5  mov     r9, rcx
0x18007f2e8  lea     r8, WPP_fa4a0884474b39b1dc1745622c5c399f_Traceguids
0x18007f2ef  call    WPP_SF__SOCKADDR_d
0x18007f2f4  test    rdi, rdi
0x18007f2f7  jnz     short loc_18007F30C
0x18007f2f9  mov     edi, 80070057h
0x18007f2fe  mov     [rbp+var_1C], 344h
0x18007f305  mov     ebx, edi
0x18007f307  jmp     loc_18007F4F3
0x18007f30c  mov     dword ptr [rdi], 1
0x18007f312  test    rbx, rbx
0x18007f315  jnz     short loc_18007F32A
0x18007f317  mov     edi, 80070057h
0x18007f31c  mov     [rbp+var_1C], 346h
0x18007f323  mov     ebx, edi
0x18007f325  jmp     loc_18007F4F3
0x18007f32a  test    r12, r12
0x18007f32d  jnz     short loc_18007F342
0x18007f32f  mov     edi, 80070057h
0x18007f334  mov     [rbp+var_1C], 347h
0x18007f33b  mov     ebx, edi
0x18007f33d  jmp     loc_18007F4F3
0x18007f342  lea     rdx, [rbp+lpMem]
0x18007f346  mov     rcx, rbx
0x18007f349  call    DdrCreateNetInfo
0x18007f34e  mov     ebx, eax
0x18007f350  test    eax, eax
0x18007f352  jle     short loc_18007F35D
0x18007f354  movzx   ebx, ax
0x18007f357  or      ebx, 80070000h
0x18007f35d  test    ebx, ebx
0x18007f35f  jns     short loc_18007F36F
0x18007f361  mov     [rbp+var_1C], 349h
0x18007f368  mov     edi, ebx
0x18007f36a  jmp     loc_18007F4F3
0x18007f36f  mov     rax, [rbp+lpMem]
0x18007f373  lea     r8, aDnsResolverArp; "_dns.resolver.arpa"
0x18007f37a  xor     ecx, ecx
0x18007f37c  mov     [rax+98h], r15d
0x18007f383  xor     eax, eax
0x18007f385  mov     [rsp+60h+var_28], ax
0x18007f38a  mov     [rsp+60h+var_30], eax
0x18007f38e  mov     [rsp+60h+var_38], 10000000h
0x18007f397  lea     r15d, [rax+1]
0x18007f39b  mov     [rsp+60h+var_40], rax
0x18007f3a0  mov     edx, r15d
0x18007f3a3  lea     r9d, [rax+40h]
0x18007f3a7  call    Dns_BuildPacketInternal
0x18007f3ac  mov     r14, rax
0x18007f3af  test    rax, rax
0x18007f3b2  jnz     short loc_18007F3C2
0x18007f3b4  mov     ebx, 8007000Eh
0x18007f3b9  mov     [rbp+var_1C], 35Ah
0x18007f3c0  jmp     short loc_18007F368
0x18007f3c2  mov     rcx, r14
0x18007f3c5  call    AddRefDnsMessage
0x18007f3ca  call    cs:__imp_GetCurrentProcessId
0x18007f3d1  nop     dword ptr [rax+rax+00h]
0x18007f3d6  lea     rcx, [rbp+pv]
0x18007f3da  mov     [r14+298h], eax
0x18007f3e1  call    Send_CreateSendBlob
0x18007f3e6  mov     ebx, eax
0x18007f3e8  test    eax, eax
0x18007f3ea  jle     short loc_18007F3F5
0x18007f3ec  movzx   ebx, ax
0x18007f3ef  or      ebx, 80070000h
0x18007f3f5  mov     rsi, [rbp+pv]
0x18007f3f9  test    ebx, ebx
0x18007f3fb  jns     short loc_18007F409
0x18007f3fd  mov     [rbp+var_1C], 35Fh
0x18007f404  jmp     loc_18007F368
0x18007f409  mov     eax, [r14+298h]
0x18007f410  mov     [rsi+1E8h], eax
0x18007f416  mov     [rsi+58h], r14
0x18007f41a  mov     rax, [rbp+lpMem]
0x18007f41e  mov     [rsi+20h], rax
0x18007f422  mov     rax, 1000000000000008h
0x18007f42c  mov     [rbp+lpMem], 0
0x18007f434  mov     [rsi+0A8h], rax
0x18007f43b  lea     rax, ?DdrQueryCallback@@YAJPEAXPEAU_SendBlob@@J@Z; DdrQueryCallback(void *,_SendBlob *,long)
0x18007f442  mov     [rsi+0B4h], r15d
0x18007f449  mov     dword ptr [rdi], 0
0x18007f44f  mov     [rsi+1D8h], rax
0x18007f456  mov     [rsi+1D0h], r12
0x18007f45d  lock add [r12], r15d
0x18007f462  lea     rcx, ?g_csDdrCleanup@@3VWxCriticalSection@@A; lpCriticalSection
0x18007f469  call    cs:__imp_EnterCriticalSection
0x18007f470  nop     dword ptr [rax+rax+00h]
0x18007f475  mov     rcx, rsi
0x18007f478  call    AddRefSendBlob
0x18007f47d  mov     rcx, cs:off_180111330
0x18007f484  lea     rdx, ?g_DdrQueryCleanupList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DdrQueryCleanupList
0x18007f48b  cmp     [rcx], rdx
0x18007f48e  jz      short loc_18007F497
0x18007f490  mov     ecx, 3
0x18007f495  int     29h; Win8: RtlFailFast(ecx)
0x18007f497  lea     rax, [rsi+280h]
0x18007f49e  xor     r14d, r14d
0x18007f4a1  mov     [rax+8], rcx
0x18007f4a5  mov     [rax], rdx
0x18007f4a8  mov     [rcx], rax
0x18007f4ab  lea     rcx, ?g_csDdrCleanup@@3VWxCriticalSection@@A; lpCriticalSection
0x18007f4b2  mov     cs:off_180111330, rax
0x18007f4b9  call    cs:__imp_LeaveCriticalSection
0x18007f4c0  nop     dword ptr [rax+rax+00h]
0x18007f4c5  mov     rcx, rsi; pv
0x18007f4c8  call    Send_AndRecv
0x18007f4cd  mov     ebx, eax
0x18007f4cf  cmp     eax, 2522h
0x18007f4d4  jz      short loc_18007F4EF
0x18007f4d6  test    eax, eax
0x18007f4d8  jle     short loc_18007F4E3
0x18007f4da  movzx   ebx, ax
0x18007f4dd  or      ebx, 80070000h
0x18007f4e3  mov     [rbp+var_1C], 37Fh
0x18007f4ea  jmp     loc_18007F368
0x18007f4ef  xor     ebx, ebx
0x18007f4f1  xor     edi, edi
0x18007f4f3  mov     rcx, [rbp+lpMem]; lpMem
0x18007f4f7  call    NetInfo_Free
0x18007f4fc  mov     rcx, r14; lpMem
0x18007f4ff  mov     [rbp+lpMem], 0
0x18007f507  call    DeRefDnsMessage
0x18007f50c  mov     rcx, rsi; lpMem
0x18007f50f  call    DeRefSendBlob
0x18007f514  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007f51b  jz      short loc_18007F536
0x18007f51d  mov     edx, 2Ch ; ','
0x18007f522  lea     r8, WPP_fa4a0884474b39b1dc1745622c5c399f_Traceguids
0x18007f529  mov     ecx, 40Bh
0x18007f52e  mov     r9d, ebx
0x18007f531  call    WPP_SF_d
0x18007f536  mov     eax, edi
0x18007f538  mov     rcx, [rbp+var_8]
0x18007f53c  xor     rcx, rsp; StackCookie
0x18007f53f  call    __security_check_cookie
0x18007f544  add     rsp, 60h
0x18007f548  pop     r15
0x18007f54a  pop     r14
0x18007f54c  pop     r12
0x18007f54e  pop     rdi
0x18007f54f  pop     rsi
0x18007f550  pop     rbx
0x18007f551  pop     rbp
0x18007f552  retn
```
