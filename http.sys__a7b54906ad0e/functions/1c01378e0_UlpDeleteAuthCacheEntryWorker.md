# UlpDeleteAuthCacheEntryWorker

- ea: `0x1c01378e0`
- end: `0x1c0137a98`
- name: `UlpDeleteAuthCacheEntryWorker`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1c0137bec`

## callees

- `0x1c0009704`
- `0x1c001a4b0`
- `0x1c008fa08`
- `0x1c009c0ec`
- `0x1c01378e0`

## import_xrefs

- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c013799f`
- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c013799f`
- `ntoskrnl!ZwClose` at `0x1c0137911`
- `ntoskrnl!ZwClose` at `0x1c0137911`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0137a42`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0137a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0137a42`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0137a6a`
- `ksecdd!DeleteSecurityContext` at `0x1c013798f`
- `ksecdd!DeleteSecurityContext` at `0x1c013798f`

## pseudocode

```c
void __fastcall UlpDeleteAuthCacheEntryWorker(__int64 a1)
{
  __int64 v1; // rbx
  bool v2; // zf
  struct _SecHandle *v3; // rcx
  NTSTATUS v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // edi
  __int64 v7; // r9
  ULONG v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // r14d
  __int64 v12; // rax
  __int64 v13; // r9
  void *v14; // rdi
  void *v15; // rdi
  __int128 v16; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h]
  char v18; // [rsp+48h] [rbp-18h]
  int v19; // [rsp+49h] [rbp-17h]
  __int16 v20; // [rsp+4Dh] [rbp-13h]
  char v21; // [rsp+4Fh] [rbp-11h]

  v1 = a1 - 96;
  v2 = *(_DWORD *)(a1 - 96 + 52) == 1;
  v3 = *(struct _SecHandle **)(a1 - 96 + 64);
  if ( v2 )
  {
    v4 = ZwClose(v3);
    v5 = *(_QWORD *)(v1 + 144);
    v6 = v4;
    if ( *(_BYTE *)(v5 + 1568) )
    {
      v7 = *(_QWORD *)(v1 + 64);
      v19 = 0;
      v20 = 0;
      v16 = 0;
      v21 = 0;
      v17 = v5;
      v18 = 0;
      McTemplateK0pq_UlEtwWriteEventWrapper(v5, HTTP_EVENT_AUTH_CACHE_ENTRY_FREED, &v16, v7, v4);
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 2) != 0 )
      WPP_SF_Dq(11, WPP_437dfdc243953413687a45c7a269a920_Traceguids, v6, *(_QWORD *)(v1 + 64));
  }
  else
  {
    v8 = DeleteSecurityContext(v3);
    v11 = RtlMapSecurityErrorToNtStatus(v8);
    v12 = *(_QWORD *)(v1 + 144);
    if ( *(_BYTE *)(v12 + 1568) )
    {
      v13 = *(_QWORD *)(v1 + 64);
      v19 = 0;
      v20 = 0;
      v16 = 0;
      v21 = 0;
      v17 = v12;
      v18 = 0;
      McTemplateK0pq_UlEtwWriteEventWrapper(v10, HTTP_EVENT_AUTH_CACHE_ENTRY_FREED, &v16, v13, v11);
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 2) != 0 )
      WPP_SF_ddq(v10, v9, v11, v8, *(_QWORD *)(v1 + 64));
    *(_QWORD *)(*(_QWORD *)(v1 + 64) + 8LL) = -1;
    **(_QWORD **)(v1 + 64) = -1;
  }
  v14 = *(void **)(v1 + 40);
  *(_QWORD *)(v1 + 144) = 0;
  if ( v14 )
  {
    memset(v14, 0, *(unsigned int *)(v1 + 48));
    ExFreePoolWithTag(*(PVOID *)(v1 + 40), 0);
  }
  v15 = *(void **)(v1 + 24);
  if ( v15 )
    memset(v15, 0, *(unsigned int *)(v1 + 32));
  *(_DWORD *)(v1 + 16) = 1903709301;
  ExFreePoolWithTag((PVOID)v1, 0);
}

```

## disassembly

```asm
0x1c01378e0  mov     [rsp-18h+arg_8], rbx
0x1c01378e5  mov     [rsp-18h+arg_10], rsi
0x1c01378ea  push    rbp
0x1c01378eb  push    rdi
0x1c01378ec  push    r14
0x1c01378ee  mov     rbp, rsp
0x1c01378f1  sub     rsp, 60h
0x1c01378f5  mov     rax, cs:__security_cookie
0x1c01378fc  xor     rax, rsp
0x1c01378ff  mov     [rbp+var_10], rax
0x1c0137903  lea     rbx, [rcx-60h]
0x1c0137907  cmp     dword ptr [rbx+34h], 1
0x1c013790b  mov     rcx, [rbx+40h]; phContext
0x1c013790f  jnz     short loc_1C013798F
0x1c0137911  call    cs:__imp_ZwClose
0x1c0137918  nop     dword ptr [rax+rax+00h]
0x1c013791d  mov     rcx, [rbx+90h]
0x1c0137924  xor     esi, esi
0x1c0137926  mov     edi, eax
0x1c0137928  cmp     [rcx+620h], sil
0x1c013792f  jz      short loc_1C0137964
0x1c0137931  mov     r9, [rbx+40h]
0x1c0137935  lea     r8, [rbp+var_30]
0x1c0137939  xorps   xmm0, xmm0
0x1c013793c  mov     [rbp+var_17], esi
0x1c013793f  lea     rdx, HTTP_EVENT_AUTH_CACHE_ENTRY_FREED
0x1c0137946  mov     [rbp+var_13], si
0x1c013794a  movdqu  [rbp+var_30], xmm0
0x1c013794f  mov     [rbp+var_11], sil
0x1c0137953  mov     [rbp+var_20], rcx
0x1c0137957  mov     [rbp+var_18], sil
0x1c013795b  mov     dword ptr [rsp+60h+var_40], eax
0x1c013795f  call    McTemplateK0pq_UlEtwWriteEventWrapper
0x1c0137964  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c013796a  test    al, 2
0x1c013796c  jz      loc_1C0137A25
0x1c0137972  mov     r9, [rbx+40h]
0x1c0137976  lea     rdx, WPP_437dfdc243953413687a45c7a269a920_Traceguids
0x1c013797d  mov     ecx, 0Bh
0x1c0137982  mov     r8d, edi
0x1c0137985  call    WPP_SF_Dq
0x1c013798a  jmp     loc_1C0137A25
0x1c013798f  call    cs:__imp_DeleteSecurityContext
0x1c0137996  nop     dword ptr [rax+rax+00h]
0x1c013799b  mov     ecx, eax; SecurityError
0x1c013799d  mov     edi, eax
0x1c013799f  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x1c01379a6  nop     dword ptr [rax+rax+00h]
0x1c01379ab  mov     r14d, eax
0x1c01379ae  xor     esi, esi
0x1c01379b0  mov     rax, [rbx+90h]
0x1c01379b7  cmp     [rax+620h], sil
0x1c01379be  jz      short loc_1C01379F4
0x1c01379c0  mov     r9, [rbx+40h]
0x1c01379c4  lea     r8, [rbp+var_30]
0x1c01379c8  xorps   xmm0, xmm0
0x1c01379cb  mov     [rbp+var_17], esi
0x1c01379ce  lea     rdx, HTTP_EVENT_AUTH_CACHE_ENTRY_FREED
0x1c01379d5  mov     [rbp+var_13], si
0x1c01379d9  movdqu  [rbp+var_30], xmm0
0x1c01379de  mov     [rbp+var_11], sil
0x1c01379e2  mov     [rbp+var_20], rax
0x1c01379e6  mov     [rbp+var_18], sil
0x1c01379ea  mov     dword ptr [rsp+60h+var_40], r14d
0x1c01379ef  call    McTemplateK0pq_UlEtwWriteEventWrapper
0x1c01379f4  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c01379fa  test    al, 2
0x1c01379fc  jz      short loc_1C0137A12
0x1c01379fe  mov     rax, [rbx+40h]
0x1c0137a02  mov     r9d, edi
0x1c0137a05  mov     r8d, r14d
0x1c0137a08  mov     [rsp+60h+var_40], rax
0x1c0137a0d  call    WPP_SF_ddq
0x1c0137a12  mov     rax, [rbx+40h]
0x1c0137a16  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1c0137a1a  mov     [rax+8], rcx
0x1c0137a1e  mov     rax, [rbx+40h]
0x1c0137a22  mov     [rax], rcx
0x1c0137a25  mov     rdi, [rbx+28h]
0x1c0137a29  mov     [rbx+90h], rsi
0x1c0137a30  test    rdi, rdi
0x1c0137a33  jz      short loc_1C0137A4E
0x1c0137a35  mov     ecx, [rbx+30h]
0x1c0137a38  xor     eax, eax
0x1c0137a3a  rep stosb
0x1c0137a3c  mov     rcx, [rbx+28h]; P
0x1c0137a40  xor     edx, edx; Tag
0x1c0137a42  call    cs:__imp_ExFreePoolWithTag
0x1c0137a49  nop     dword ptr [rax+rax+00h]
0x1c0137a4e  mov     rdi, [rbx+18h]
0x1c0137a52  test    rdi, rdi
0x1c0137a55  jz      short loc_1C0137A5E
0x1c0137a57  mov     ecx, [rbx+20h]
0x1c0137a5a  xor     eax, eax
0x1c0137a5c  rep stosb
0x1c0137a5e  xor     edx, edx; Tag
0x1c0137a60  mov     dword ptr [rbx+10h], 71784C75h
0x1c0137a67  mov     rcx, rbx; P
0x1c0137a6a  call    cs:__imp_ExFreePoolWithTag
0x1c0137a71  nop     dword ptr [rax+rax+00h]
0x1c0137a76  mov     rcx, [rbp+var_10]
0x1c0137a7a  xor     rcx, rsp; StackCookie
0x1c0137a7d  call    __security_check_cookie
0x1c0137a82  lea     r11, [rsp+60h+var_s0]
0x1c0137a87  mov     rbx, [r11+28h]
0x1c0137a8b  mov     rsi, [r11+30h]
0x1c0137a8f  mov     rsp, r11
0x1c0137a92  pop     r14
0x1c0137a94  pop     rdi
0x1c0137a95  pop     rbp
0x1c0137a96  retn
```
