# MdaCleanupFobx

- ea: `0x140030b60`
- end: `0x140030ee0`
- name: `MdaCleanupFobx`
- size: `896`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation`

## callees

- `0x140008140`
- `0x1400145f0`
- `0x140014970`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x14001f178`
- `0x14002f57c`
- `0x140030b60`
- `0x140033af0`
- `0x140033c50`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x140030d5c`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140030d5c`
- `ntoskrnl!KeReleaseMutex` at `0x140030cd6`
- `ntoskrnl!KeReleaseMutex` at `0x140030d3e`
- `ntoskrnl!KeReleaseMutex` at `0x140030e6c`
- `ntoskrnl!KeReleaseMutex` at `0x140030cd6`
- `ntoskrnl!KeReleaseMutex` at `0x140030d3e`
- `ntoskrnl!KeReleaseMutex` at `0x140030e6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c39`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030c39`

## pseudocode

```c
__int64 __fastcall MdaCleanupFobx(_QWORD *a1, __int64 a2)
{
  __int64 v2; // rbp
  unsigned __int16 *v4; // r15
  __int64 v5; // r13
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // r12
  void *v9; // rcx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r14
  __int64 v13; // rdi
  __int64 v14; // rcx
  IRP *v15; // rcx
  ULONG RequestorProcessId; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  int v21; // edi
  __int128 v23; // [rsp+20h] [rbp-68h] BYREF
  __int128 v24; // [rsp+30h] [rbp-58h]
  __int64 v25; // [rsp+90h] [rbp+8h]

  v2 = a1[8];
  v4 = (unsigned __int16 *)a1[7];
  v25 = a1[10];
  v5 = *(_QWORD *)(v2 + 32);
  v6 = *((_QWORD *)v4 + 17);
  v7 = *(_QWORD *)(v2 + 56);
  v8 = *(_QWORD *)(v5 + 40);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          122,
          WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
          a1[7] + 360LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, *v4);
    }
  }
  if ( v7 )
  {
    v9 = *(void **)(v7 + 64);
    if ( v9 )
    {
      ExFreePoolWithTag(v9, 0);
      *(_QWORD *)(v7 + 64) = 0;
    }
    if ( *(_QWORD *)(v7 + 8) )
    {
      LOBYTE(a2) = 1;
      NfsReadDirectoryQuit(v7 + 8, a2);
    }
  }
  if ( *v4 == 0xEC24 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      v11 = 124;
LABEL_48:
      WPP_SF_(v10->AttachedDevice, v11, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    }
  }
  else
  {
    v12 = *(_QWORD *)(v8 + 40);
    v13 = *(_QWORD *)(*(_QWORD *)(v8 + 32) + 40LL);
    HacAcquireLock(*(_QWORD *)(v6 + 8));
    if ( *(_DWORD *)(*(_QWORD *)(v6 + 8) + 128LL) == 2 )
      MdaNotifyCleanup(*(PFAST_MUTEX *)(v13 + 104));
    if ( (*(_DWORD *)(v5 + 72) & 0x400) != 0 )
    {
      KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v6 + 8) + 40LL), 0);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        v11 = 125;
        goto LABEL_48;
      }
    }
    else
    {
      if ( (*(_DWORD *)(v12 + 32) & 1) != 0 && (v14 = *(_QWORD *)(v6 + 8), *(_DWORD *)(v14 + 128) == 1) )
      {
        v23 = 0;
        v24 = 0;
        KeReleaseMutex(*(PRKMUTEX *)(v14 + 40), 0);
        v15 = (IRP *)a1[5];
        *((_QWORD *)&v23 + 1) = *(_QWORD *)(v6 + 8);
        *(_QWORD *)&v23 = v8;
        RequestorProcessId = IoGetRequestorProcessId(v15);
        v17 = *(unsigned int *)(v5 + 124);
        LODWORD(v24) = RequestorProcessId;
        v18 = MdaMapShareAccess(v17);
        v19 = *(unsigned int *)(v5 + 120);
        DWORD1(v24) = v18;
        DWORD2(v24) = MdaMapDesiredAccess(v19);
        if ( *(_QWORD *)((char *)&v24 + 4) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_Z(
              WPP_GLOBAL_Control->AttachedDevice,
              126,
              WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
              *(_QWORD *)(v6 + 8) + 64LL);
          }
          v20 = NlmShareOrUnshare(a1, &v23, 21);
          v21 = v20;
          if ( v20 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                127,
                WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                (unsigned int)v20);
            }
            if ( v21 == -1073741816 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_Z(
                  WPP_GLOBAL_Control->AttachedDevice,
                  128,
                  WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
                  *(_QWORD *)(v6 + 8) + 64LL);
              }
              HacOrphanStaleEntry(v25, *(_QWORD *)(v6 + 8));
            }
          }
        }
      }
      else
      {
        KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v6 + 8) + 40LL), 0);
      }
      if ( (*((_DWORD *)v4 + 39) & 0x80u) == 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        {
          v11 = 130;
          goto LABEL_48;
        }
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          v11 = 129;
          goto LABEL_48;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140030b60  push    rbx
0x140030b62  push    rbp
0x140030b63  push    rsi
0x140030b64  push    rdi
0x140030b65  push    r12
0x140030b67  push    r13
0x140030b69  push    r14
0x140030b6b  push    r15
0x140030b6d  sub     rsp, 48h
0x140030b71  mov     rbp, [rcx+40h]
0x140030b75  mov     rsi, rcx
0x140030b78  mov     r15, [rcx+38h]
0x140030b7c  mov     rax, [rcx+50h]
0x140030b80  mov     [rsp+88h+arg_0], rax
0x140030b88  mov     r13, [rbp+20h]
0x140030b8c  mov     rbx, [r15+88h]
0x140030b93  mov     rdi, [rbp+38h]
0x140030b97  mov     r12, [r13+28h]
0x140030b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ba2  lea     r14, WPP_GLOBAL_Control
0x140030ba9  cmp     rcx, r14
0x140030bac  jz      short loc_140030C29
0x140030bae  mov     eax, [rcx+2Ch]
0x140030bb1  test    al, 8
0x140030bb3  jz      short loc_140030BCA
0x140030bb5  mov     rcx, [rcx+18h]
0x140030bb9  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030bc0  mov     edx, 79h ; 'y'
0x140030bc5  call    WPP_SF_
0x140030bca  mov     rcx, cs:WPP_GLOBAL_Control
0x140030bd1  cmp     rcx, r14
0x140030bd4  jz      short loc_140030C29
0x140030bd6  mov     eax, [rcx+2Ch]
0x140030bd9  test    al, 4
0x140030bdb  jz      short loc_140030BFD
0x140030bdd  mov     r9, [rsi+38h]
0x140030be1  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030be8  mov     rcx, [rcx+18h]
0x140030bec  add     r9, 168h
0x140030bf3  mov     edx, 7Ah ; 'z'
0x140030bf8  call    WPP_SF_Z
0x140030bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c04  cmp     rcx, r14
0x140030c07  jz      short loc_140030C29
0x140030c09  mov     eax, [rcx+2Ch]
0x140030c0c  test    al, 4
0x140030c0e  jz      short loc_140030C29
0x140030c10  movzx   r9d, word ptr [r15]
0x140030c14  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030c1b  mov     rcx, [rcx+18h]
0x140030c1f  mov     edx, 7Bh ; '{'
0x140030c24  call    WPP_SF_d
0x140030c29  test    rdi, rdi
0x140030c2c  jz      short loc_140030C5E
0x140030c2e  mov     rcx, [rdi+40h]; P
0x140030c32  test    rcx, rcx
0x140030c35  jz      short loc_140030C4D
0x140030c37  xor     edx, edx; Tag
0x140030c39  call    cs:__imp_ExFreePoolWithTag
0x140030c40  nop     dword ptr [rax+rax+00h]
0x140030c45  mov     qword ptr [rdi+40h], 0
0x140030c4d  lea     rcx, [rdi+8]
0x140030c51  cmp     qword ptr [rcx], 0
0x140030c55  jz      short loc_140030C5E
0x140030c57  mov     dl, 1
0x140030c59  call    NfsReadDirectoryQuit
0x140030c5e  mov     eax, 0EC24h
0x140030c63  cmp     [r15], ax
0x140030c67  jnz     short loc_140030C8E
0x140030c69  mov     rcx, cs:WPP_GLOBAL_Control
0x140030c70  cmp     rcx, r14
0x140030c73  jz      loc_140030ECC
0x140030c79  mov     eax, [rcx+2Ch]
0x140030c7c  test    al, 8
0x140030c7e  jz      loc_140030ECC
0x140030c84  mov     edx, 7Ch ; '|'
0x140030c89  jmp     loc_140030EBC
0x140030c8e  mov     rax, [r12+20h]
0x140030c93  mov     rcx, [rbx+8]
0x140030c97  mov     r14, [r12+28h]
0x140030c9c  mov     rdi, [rax+28h]
0x140030ca0  call    HacAcquireLock
0x140030ca5  mov     rax, [rbx+8]
0x140030ca9  cmp     dword ptr [rax+80h], 2
0x140030cb0  jnz     short loc_140030CC2
0x140030cb2  mov     rcx, [rdi+68h]; FastMutex
0x140030cb6  lea     rdx, [rdi+58h]
0x140030cba  mov     r8, rbp
0x140030cbd  call    MdaNotifyCleanup
0x140030cc2  test    dword ptr [r13+48h], 400h
0x140030cca  jz      short loc_140030D0E
0x140030ccc  mov     rcx, [rbx+8]
0x140030cd0  xor     edx, edx; Wait
0x140030cd2  mov     rcx, [rcx+28h]; Mutex
0x140030cd6  call    cs:__imp_KeReleaseMutex
0x140030cdd  nop     dword ptr [rax+rax+00h]
0x140030ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x140030ce9  lea     rbp, WPP_GLOBAL_Control
0x140030cf0  cmp     rcx, rbp
0x140030cf3  jz      loc_140030ECC
0x140030cf9  mov     eax, [rcx+2Ch]
0x140030cfc  test    al, 2
0x140030cfe  jz      loc_140030ECC
0x140030d04  mov     edx, 7Dh ; '}'
0x140030d09  jmp     loc_140030EBC
0x140030d0e  mov     eax, [r14+20h]
0x140030d12  test    al, 1
0x140030d14  jz      loc_140030E62
0x140030d1a  mov     rcx, [rbx+8]
0x140030d1e  cmp     dword ptr [rcx+80h], 1
0x140030d25  jnz     loc_140030E62
0x140030d2b  xorps   xmm0, xmm0
0x140030d2e  xor     edx, edx; Wait
0x140030d30  movups  [rsp+88h+var_68], xmm0
0x140030d35  movups  [rsp+88h+var_58], xmm0
0x140030d3a  mov     rcx, [rcx+28h]; Mutex
0x140030d3e  call    cs:__imp_KeReleaseMutex
0x140030d45  nop     dword ptr [rax+rax+00h]
0x140030d4a  mov     rax, [rbx+8]
0x140030d4e  mov     rcx, [rsi+28h]; Irp
0x140030d52  mov     qword ptr [rsp+88h+var_68+8], rax
0x140030d57  mov     qword ptr [rsp+88h+var_68], r12
0x140030d5c  call    cs:__imp_IoGetRequestorProcessId
0x140030d63  nop     dword ptr [rax+rax+00h]
0x140030d68  mov     ecx, [r13+7Ch]
0x140030d6c  mov     dword ptr [rsp+88h+var_58], eax
0x140030d70  call    MdaMapShareAccess
0x140030d75  mov     ecx, [r13+78h]
0x140030d79  mov     dword ptr [rsp+88h+var_58+4], eax
0x140030d7d  call    MdaMapDesiredAccess
0x140030d82  cmp     dword ptr [rsp+88h+var_58+4], 0
0x140030d87  mov     dword ptr [rsp+88h+var_58+8], eax
0x140030d8b  jnz     short loc_140030D95
0x140030d8d  test    eax, eax
0x140030d8f  jz      loc_140030E78
0x140030d95  mov     rcx, cs:WPP_GLOBAL_Control
0x140030d9c  lea     rbp, WPP_GLOBAL_Control
0x140030da3  cmp     rcx, rbp
0x140030da6  jz      short loc_140030DCE
0x140030da8  test    dword ptr [rcx+2Ch], 40000h
0x140030daf  jz      short loc_140030DCE
0x140030db1  mov     r9, [rbx+8]
0x140030db5  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030dbc  mov     rcx, [rcx+18h]
0x140030dc0  add     r9, 40h ; '@'
0x140030dc4  mov     edx, 7Eh ; '~'
0x140030dc9  call    WPP_SF_Z
0x140030dce  mov     r8d, 15h
0x140030dd4  lea     rdx, [rsp+88h+var_68]
0x140030dd9  mov     rcx, rsi
0x140030ddc  call    NlmShareOrUnshare
0x140030de1  mov     edi, eax
0x140030de3  test    eax, eax
0x140030de5  jns     loc_140030E7F
0x140030deb  mov     rcx, cs:WPP_GLOBAL_Control
0x140030df2  cmp     rcx, rbp
0x140030df5  jz      short loc_140030E17
0x140030df7  mov     edx, [rcx+2Ch]
0x140030dfa  test    dl, 1
0x140030dfd  jz      short loc_140030E17
0x140030dff  mov     rcx, [rcx+18h]
0x140030e03  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030e0a  mov     edx, 7Fh
0x140030e0f  mov     r9d, eax
0x140030e12  call    WPP_SF_d
0x140030e17  cmp     edi, 0C0000008h
0x140030e1d  jnz     short loc_140030E7F
0x140030e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e26  cmp     rcx, rbp
0x140030e29  jz      short loc_140030E4F
0x140030e2b  mov     eax, [rcx+2Ch]
0x140030e2e  test    al, 1
0x140030e30  jz      short loc_140030E4F
0x140030e32  mov     r9, [rbx+8]
0x140030e36  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030e3d  mov     rcx, [rcx+18h]
0x140030e41  add     r9, 40h ; '@'
0x140030e45  mov     edx, 80h
0x140030e4a  call    WPP_SF_Z
0x140030e4f  mov     rdx, [rbx+8]
0x140030e53  mov     rcx, [rsp+88h+arg_0]
0x140030e5b  call    HacOrphanStaleEntry
0x140030e60  jmp     short loc_140030E7F
0x140030e62  mov     rcx, [rbx+8]
0x140030e66  xor     edx, edx; Wait
0x140030e68  mov     rcx, [rcx+28h]; Mutex
0x140030e6c  call    cs:__imp_KeReleaseMutex
0x140030e73  nop     dword ptr [rax+rax+00h]
0x140030e78  lea     rbp, WPP_GLOBAL_Control
0x140030e7f  mov     eax, [r15+9Ch]
0x140030e86  test    al, al
0x140030e88  jns     short loc_140030EA4
0x140030e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030e91  cmp     rcx, rbp
0x140030e94  jz      short loc_140030ECC
0x140030e96  mov     eax, [rcx+2Ch]
0x140030e99  test    al, 2
0x140030e9b  jz      short loc_140030ECC
0x140030e9d  mov     edx, 81h
0x140030ea2  jmp     short loc_140030EBC
0x140030ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140030eab  cmp     rcx, rbp
0x140030eae  jz      short loc_140030ECC
0x140030eb0  mov     eax, [rcx+2Ch]
0x140030eb3  test    al, 8
0x140030eb5  jz      short loc_140030ECC
0x140030eb7  mov     edx, 82h
0x140030ebc  mov     rcx, [rcx+18h]
0x140030ec0  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030ec7  call    WPP_SF_
0x140030ecc  xor     eax, eax
0x140030ece  add     rsp, 48h
0x140030ed2  pop     r15
0x140030ed4  pop     r14
0x140030ed6  pop     r13
0x140030ed8  pop     r12
0x140030eda  pop     rdi
0x140030edb  pop     rsi
0x140030edc  pop     rbp
0x140030edd  pop     rbx
0x140030ede  retn
```
