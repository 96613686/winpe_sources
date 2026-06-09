# DiscpAddRemoveRADIUSServerForHBA

- ea: `0x180004af8`
- end: `0x180004cef`
- name: `DiscpAddRemoveRADIUSServerForHBA`
- size: `503`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180003f80`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180004af8`
- `0x180006998`
- `0x180016d20`

## import_xrefs

- `ISCSIUM!DiscpExecuteMethod` at `0x180004c00`
- `ISCSIUM!DiscpExecuteMethod` at `0x180004c9d`
- `ISCSIUM!DiscpExecuteMethod` at `0x180004c00`
- `ISCSIUM!DiscpExecuteMethod` at `0x180004c9d`
- `ISCSIUM!DiscpFreeMemory` at `0x180004c16`
- `ISCSIUM!DiscpFreeMemory` at `0x180004cb3`
- `ISCSIUM!DiscpFreeMemory` at `0x180004cc8`
- `ISCSIUM!DiscpFreeMemory` at `0x180004c16`
- `ISCSIUM!DiscpFreeMemory` at `0x180004cb3`
- `ISCSIUM!DiscpFreeMemory` at `0x180004cc8`

## pseudocode

```c
__int64 __fastcall DiscpAddRemoveRADIUSServerForHBA(__int64 a1, char a2)
{
  unsigned int InitiatorInstanceList; // esi
  __int64 v5; // r15
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rcx
  int v12; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v13; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[560]; // [rsp+70h] [rbp-90h] BYREF

  v13 = 0;
  v15 = 0;
  memset_0(v16, 0, 0x224u);
  v14 = 0;
  v12 = 0;
  InitiatorInstanceList = DiscpGetInitiatorInstanceList(0, &v13, &v15);
  if ( !InitiatorInstanceList )
  {
    v5 = v15;
    if ( v13 )
    {
      v6 = 0;
      if ( a2 )
      {
        do
        {
          v7 = *(_QWORD *)(v5 + 8 * v6);
          v12 = 280;
          v14 = 0;
          v8 = *(unsigned int *)(v7 + 20);
          LOBYTE(v8) = v8 & 1;
          InitiatorInstanceList = DiscpBuildIScsiIpAddress(v8, a1, 0, v16);
          if ( !InitiatorInstanceList )
            DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, *(_QWORD *)(v7 + 40), 103, v16, 548, &v14, &v12, 4);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 16), 0xFFFFFFFF) == 1 )
            DiscpFreeMemory(v7);
          v6 = (unsigned int)(v6 + 1);
        }
        while ( (unsigned int)v6 < v13 );
      }
      else
      {
        do
        {
          v9 = *(_QWORD *)(v5 + 8 * v6);
          v12 = 280;
          v14 = 0;
          v10 = *(unsigned int *)(v9 + 20);
          LOBYTE(v10) = v10 & 1;
          InitiatorInstanceList = DiscpBuildIScsiIpAddress(v10, a1, 0, v16);
          if ( !InitiatorInstanceList )
            DiscpExecuteMethod(MSiSCSI_Operations_GUID, 0, *(_QWORD *)(v9 + 40), 104, v16, 548, &v14, &v12, 4);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 16), 0xFFFFFFFF) == 1 )
            DiscpFreeMemory(v9);
          v6 = (unsigned int)(v6 + 1);
        }
        while ( (unsigned int)v6 < v13 );
      }
    }
    DiscpFreeMemory(v5);
  }
  return InitiatorInstanceList;
}

```

## disassembly

```asm
0x180004af8  push    rbp
0x180004afa  push    rbx
0x180004afb  push    rsi
0x180004afc  push    rdi
0x180004afd  push    r12
0x180004aff  push    r15
0x180004b01  lea     rbp, [rsp-1B8h]
0x180004b09  sub     rsp, 2B8h
0x180004b10  mov     rax, cs:__security_cookie
0x180004b17  xor     rax, rsp
0x180004b1a  mov     [rbp+1E0h+var_40], rax
0x180004b21  mov     dil, dl
0x180004b24  mov     [rsp+2E0h+var_28C], 0
0x180004b2c  mov     r12, rcx
0x180004b2f  mov     [rsp+2E0h+var_280], 0
0x180004b38  xor     edx, edx; Val
0x180004b3a  lea     rcx, [rsp+2E0h+var_270]; void *
0x180004b3f  mov     r8d, 224h; Size
0x180004b45  call    memset_0
0x180004b4a  lea     r8, [rsp+2E0h+var_280]
0x180004b4f  mov     [rsp+2E0h+var_288], 0
0x180004b58  lea     rdx, [rsp+2E0h+var_28C]
0x180004b5d  mov     [rsp+2E0h+var_290], 0
0x180004b65  xor     ecx, ecx
0x180004b67  call    DiscpGetInitiatorInstanceList
0x180004b6c  mov     esi, eax
0x180004b6e  test    eax, eax
0x180004b70  jnz     loc_180004CCE
0x180004b76  mov     r15, [rsp+2E0h+var_280]
0x180004b7b  cmp     [rsp+2E0h+var_28C], eax
0x180004b7f  jbe     loc_180004CC5
0x180004b85  xor     ebx, ebx
0x180004b87  test    dil, dil
0x180004b8a  jz      loc_180004C2D
0x180004b90  mov     rdi, [r15+rbx*8]
0x180004b94  lea     r9, [rsp+2E0h+var_270]
0x180004b99  mov     [rsp+2E0h+var_290], 118h
0x180004ba1  xor     r8d, r8d
0x180004ba4  mov     [rsp+2E0h+var_288], 0
0x180004bad  mov     rdx, r12
0x180004bb0  mov     ecx, [rdi+14h]
0x180004bb3  and     cl, 1
0x180004bb6  call    DiscpBuildIScsiIpAddress
0x180004bbb  mov     esi, eax
0x180004bbd  test    eax, eax
0x180004bbf  jnz     short loc_180004C06
0x180004bc1  mov     r8, [rdi+28h]
0x180004bc5  lea     rax, [rsp+2E0h+var_290]
0x180004bca  mov     [rsp+2E0h+var_2A0], 4
0x180004bd2  lea     r9d, [rsi+67h]
0x180004bd6  mov     [rsp+2E0h+var_2A8], rax
0x180004bdb  lea     rcx, MSiSCSI_Operations_GUID
0x180004be2  lea     rax, [rsp+2E0h+var_288]
0x180004be7  xor     edx, edx
0x180004be9  mov     [rsp+2E0h+var_2B0], rax
0x180004bee  lea     rax, [rsp+2E0h+var_270]
0x180004bf3  mov     [rsp+2E0h+var_2B8], 224h
0x180004bfb  mov     [rsp+2E0h+var_2C0], rax
0x180004c00  call    cs:__imp_DiscpExecuteMethod
0x180004c06  or      eax, 0FFFFFFFFh
0x180004c09  lock xadd [rdi+10h], eax
0x180004c0e  cmp     eax, 1
0x180004c11  jnz     short loc_180004C1C
0x180004c13  mov     rcx, rdi
0x180004c16  call    cs:__imp_DiscpFreeMemory
0x180004c1c  inc     ebx
0x180004c1e  cmp     ebx, [rsp+2E0h+var_28C]
0x180004c22  jb      loc_180004B90
0x180004c28  jmp     loc_180004CC5
0x180004c2d  mov     rdi, [r15+rbx*8]
0x180004c31  lea     r9, [rsp+2E0h+var_270]
0x180004c36  mov     [rsp+2E0h+var_290], 118h
0x180004c3e  xor     r8d, r8d
0x180004c41  mov     [rsp+2E0h+var_288], 0
0x180004c4a  mov     rdx, r12
0x180004c4d  mov     ecx, [rdi+14h]
0x180004c50  and     cl, 1
0x180004c53  call    DiscpBuildIScsiIpAddress
0x180004c58  mov     esi, eax
0x180004c5a  test    eax, eax
0x180004c5c  jnz     short loc_180004CA3
0x180004c5e  mov     r8, [rdi+28h]
0x180004c62  lea     rax, [rsp+2E0h+var_290]
0x180004c67  mov     [rsp+2E0h+var_2A0], 4
0x180004c6f  lea     r9d, [rsi+68h]
0x180004c73  mov     [rsp+2E0h+var_2A8], rax
0x180004c78  lea     rcx, MSiSCSI_Operations_GUID
0x180004c7f  lea     rax, [rsp+2E0h+var_288]
0x180004c84  xor     edx, edx
0x180004c86  mov     [rsp+2E0h+var_2B0], rax
0x180004c8b  lea     rax, [rsp+2E0h+var_270]
0x180004c90  mov     [rsp+2E0h+var_2B8], 224h
0x180004c98  mov     [rsp+2E0h+var_2C0], rax
0x180004c9d  call    cs:__imp_DiscpExecuteMethod
0x180004ca3  or      eax, 0FFFFFFFFh
0x180004ca6  lock xadd [rdi+10h], eax
0x180004cab  cmp     eax, 1
0x180004cae  jnz     short loc_180004CB9
0x180004cb0  mov     rcx, rdi
0x180004cb3  call    cs:__imp_DiscpFreeMemory
0x180004cb9  inc     ebx
0x180004cbb  cmp     ebx, [rsp+2E0h+var_28C]
0x180004cbf  jb      loc_180004C2D
0x180004cc5  mov     rcx, r15
0x180004cc8  call    cs:__imp_DiscpFreeMemory
0x180004cce  mov     eax, esi
0x180004cd0  mov     rcx, [rbp+1E0h+var_40]
0x180004cd7  xor     rcx, rsp; StackCookie
0x180004cda  call    __security_check_cookie
0x180004cdf  add     rsp, 2B8h
0x180004ce6  pop     r15
0x180004ce8  pop     r12
0x180004cea  pop     rdi
0x180004ceb  pop     rsi
0x180004cec  pop     rbx
0x180004ced  pop     rbp
0x180004cee  retn
```
