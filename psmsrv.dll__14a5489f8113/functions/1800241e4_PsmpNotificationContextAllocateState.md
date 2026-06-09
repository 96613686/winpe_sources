# PsmpNotificationContextAllocateState

- ea: `0x1800241e4`
- end: `0x1800242a2`
- name: `PsmpNotificationContextAllocateState`
- size: `190`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800242a8`

## callees

- `0x18001b7e0`
- `0x18001c10c`
- `0x1800241e4`
- `0x18002dbd0`
- `0x18002dd34`
- `0x18002de14`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180024226`
- `ntdll!RtlCopySid` at `0x180024226`

## pseudocode

```c
__int64 __fastcall PsmpNotificationContextAllocateState(__int64 a1, void *a2)
{
  __int64 result; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  _BYTE DestinationSid[80]; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE pSid[80]; // [rsp+80h] [rbp-68h] BYREF

  memset_0(DestinationSid, 0, 0x44u);
  RtlCopySid(0x44u, DestinationSid, a2);
  memset_0(pSid, 0, 0x44u);
  result = RmpWnfGetPublisherSid(pSid);
  if ( (int)result >= 0 )
  {
    result = RmpWnfCreateStateNameForIpcEx(pSid, DestinationSid, v5, v6, (struct _WNF_STATE_NAME *)(a1 + 124));
    if ( (int)result >= 0 )
    {
      result = RmpWnfAllocateAndInitializePendingCallbackList(a1 + 136);
      if ( (int)result >= 0 )
        return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800241e4  mov     [rsp+arg_10], rbx
0x1800241e9  push    rdi
0x1800241ea  sub     rsp, 0E0h
0x1800241f1  mov     rax, cs:__security_cookie
0x1800241f8  xor     rax, rsp
0x1800241fb  mov     [rsp+0E8h+var_18], rax
0x180024203  mov     rbx, rdx
0x180024206  mov     rdi, rcx
0x180024209  xor     edx, edx; Val
0x18002420b  lea     rcx, [rsp+0E8h+DestinationSid]; void *
0x180024210  lea     r8d, [rdx+44h]; Size
0x180024214  call    memset_0
0x180024219  mov     r8, rbx; SourceSid
0x18002421c  lea     rdx, [rsp+0E8h+DestinationSid]; DestinationSid
0x180024221  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180024226  call    cs:__imp_RtlCopySid
0x18002422c  xor     edx, edx; Val
0x18002422e  lea     rcx, [rsp+0E8h+pSid]; void *
0x180024236  lea     r8d, [rdx+44h]; Size
0x18002423a  call    memset_0
0x18002423f  lea     rcx, [rsp+0E8h+pSid]; DestinationSid
0x180024247  call    RmpWnfGetPublisherSid
0x18002424c  test    eax, eax
0x18002424e  js      short loc_180024281
0x180024250  lea     rax, [rdi+7Ch]
0x180024254  lea     rdx, [rsp+0E8h+DestinationSid]; PSID
0x180024259  mov     [rsp+0E8h+var_C8], rax; struct _WNF_STATE_NAME *
0x18002425e  lea     rcx, [rsp+0E8h+pSid]; pSid
0x180024266  call    ?RmpWnfCreateStateNameForIpcEx@@YAJPEAT_RM_SID@@0KKPEAU_WNF_STATE_NAME@@@Z; RmpWnfCreateStateNameForIpcEx(_RM_SID *,_RM_SID *,ulong,ulong,_WNF_STATE_NAME *)
0x18002426b  test    eax, eax
0x18002426d  js      short loc_180024281
0x18002426f  lea     rcx, [rdi+88h]
0x180024276  call    RmpWnfAllocateAndInitializePendingCallbackList
0x18002427b  test    eax, eax
0x18002427d  js      short loc_180024281
0x18002427f  xor     eax, eax
0x180024281  mov     rcx, [rsp+0E8h+var_18]
0x180024289  xor     rcx, rsp; StackCookie
0x18002428c  call    __security_check_cookie
0x180024291  mov     rbx, [rsp+0E8h+arg_10]
0x180024299  add     rsp, 0E0h
0x1800242a0  pop     rdi
0x1800242a1  retn
```
