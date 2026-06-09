# RefsUserFsRequest

- ea: `0x1c015c128`
- end: `0x1c015c35f`
- name: `RefsUserFsRequest`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `77`
- tags: ``

## callers

- `0x1c015c010`

## callees

- `0x1c000f770`
- `0x1c0013f90`
- `0x1c00592b0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c0093e78`
- `0x1c009629c`
- `0x1c00987c4`
- `0x1c009896c`
- `0x1c0099458`
- `0x1c015c128`
- `0x1c015c368`
- `0x1c017bc44`
- `0x1c017bd84`
- `0x1c017c2e0`
- `0x1c017c990`
- `0x1c017d178`
- `0x1c017d230`
- `0x1c01973a0`
- `0x1c01a5384`
- `0x1c01a629c`
- `0x1c01a6828`
- `0x1c01a6cd0`
- `0x1c01a738c`
- `0x1c01a7610`
- `0x1c01a8c00`
- `0x1c01a8fe4`
- `0x1c01a9250`
- `0x1c01aa164`
- `0x1c01aa5d4`
- `0x1c01aa9b0`
- `0x1c01ab2f8`
- `0x1c01abff4`
- `0x1c01ac238`
- `0x1c01ac9fc`
- `0x1c01acda4`
- `0x1c01ad5ac`
- `0x1c01ad7d0`
- `0x1c01aeb10`
- `0x1c01af498`
- `0x1c01af5ac`
- `0x1c01b03d0`
- `0x1c01b0f64`
- `0x1c01b18f8`
- `0x1c01b1f28`
- `0x1c01b2934`
- `0x1c01b2d90`
- `0x1c01b3260`
- `0x1c01b35c0`
- `0x1c01b3910`

## import_xrefs

- `ntoskrnl!IoGetIoPriorityHint` at `0x1c018323a`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1c018323a`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1c0183210`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1c0183210`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x1c018324b`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x1c018324b`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1c017e944`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1c0183283`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1c017e944`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1c0183283`

## pseudocode

```c

```

## disassembly

```asm
0x1c015c128  mov     [rsp+arg_10], rbx
0x1c015c12d  mov     [rsp+arg_18], rsi
0x1c015c132  push    rdi
0x1c015c133  sub     rsp, 40h
0x1c015c137  mov     rax, cs:__security_cookie
0x1c015c13e  xor     rax, rsp
0x1c015c141  mov     [rsp+48h+var_10], rax
0x1c015c146  mov     rsi, rdx
0x1c015c149  mov     rdi, rcx
0x1c015c14c  mov     rax, [rdx+0B8h]
0x1c015c153  mov     ecx, [rax+18h]
0x1c015c156  mov     eax, 9023Ch
0x1c015c15b  cmp     ecx, eax
0x1c015c15d  jbe     short loc_1C015C1D7
0x1c015c15f  mov     eax, 903D8h
0x1c015c164  cmp     ecx, eax
0x1c015c166  ja      loc_1C01833F3
0x1c015c16c  jz      loc_1C01833E5
0x1c015c172  mov     eax, 9037Bh
0x1c015c177  cmp     ecx, eax
0x1c015c179  ja      loc_1C0183326
0x1c015c17f  jz      loc_1C0183318
0x1c015c185  mov     eax, 902D0h
0x1c015c18a  cmp     ecx, eax
0x1c015c18c  ja      loc_1C01832C2
0x1c015c192  jz      loc_1C01832B4
0x1c015c198  sub     ecx, 90240h
0x1c015c19e  jz      loc_1C0182F5E
0x1c015c1a4  sub     ecx, 30h ; '0'
0x1c015c1a7  jnz     loc_1C015C2B4
0x1c015c1ad  mov     rcx, rdi
0x1c015c1b0  call    RefsSetPurgeFailureMode
0x1c015c1b5  mov     ebx, eax
0x1c015c1b7  mov     eax, ebx
0x1c015c1b9  mov     rcx, [rsp+48h+var_10]
0x1c015c1be  xor     rcx, rsp; StackCookie
0x1c015c1c1  call    __security_check_cookie
0x1c015c1c6  mov     rbx, [rsp+48h+arg_10]
0x1c015c1cb  mov     rsi, [rsp+48h+arg_18]
0x1c015c1d0  add     rsp, 40h
0x1c015c1d4  pop     rdi
0x1c015c1d5  retn
0x1c015c1d7  jz      loc_1C01831AE
0x1c015c1dd  mov     eax, 90078h
0x1c015c1e2  cmp     ecx, eax
0x1c015c1e4  jz      loc_1C015C2A7
0x1c015c1ea  ja      loc_1C015C2FD
0x1c015c1f0  mov     eax, 9002Ch
0x1c015c1f5  cmp     ecx, eax
0x1c015c1f7  jbe     loc_1C015C2D0
0x1c015c1fd  sub     ecx, 90030h
0x1c015c203  jz      loc_1C0183027
0x1c015c209  sub     ecx, 0Bh
0x1c015c20c  jz      loc_1C0183019
0x1c015c212  sub     ecx, 1
0x1c015c215  jz      loc_1C018300B
0x1c015c21b  sub     ecx, 14h
0x1c015c21e  jz      loc_1C0182F5E
0x1c015c224  sub     ecx, 0Ch
0x1c015c227  jz      loc_1C0182F5E
0x1c015c22d  sub     ecx, 4
0x1c015c230  jz      loc_1C0182FFD
0x1c015c236  sub     ecx, 0Fh
0x1c015c239  jz      loc_1C0182FEF
0x1c015c23f  sub     ecx, 4
0x1c015c242  jz      loc_1C0182FD6
0x1c015c248  cmp     ecx, 1
0x1c015c24b  jz      loc_1C0182FB7
0x1c015c251  lea     rax, WPP_GLOBAL_Control
0x1c015c258  mov     rcx, cs:WPP_GLOBAL_Control
0x1c015c25f  cmp     rcx, rax
0x1c015c262  jz      short loc_1C015C271
0x1c015c264  test    dword ptr [rcx+2Ch], 100h
0x1c015c26b  jnz     loc_1C018356C
0x1c015c271  mov     ebx, 0C0000010h
0x1c015c276  mov     al, cs:RefsStatusDebugEnabled
0x1c015c27c  test    al, al
0x1c015c27e  jz      short loc_1C015C294
0x1c015c280  mov     r8d, 7FBh
0x1c015c286  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c015c28d  mov     ecx, ebx; Status
0x1c015c28f  call    RefsStatusDebug
0x1c015c294  mov     r8d, ebx
0x1c015c297  mov     rdx, rsi
0x1c015c29a  mov     rcx, rdi
0x1c015c29d  call    RefsCompleteFileSystemControlRequest
0x1c015c2a2  jmp     loc_1C015C1B7
0x1c015c2a7  mov     rcx, rdi
0x1c015c2aa  call    RefsIsVolumeDirty
0x1c015c2af  jmp     loc_1C015C1B5
0x1c015c2b4  sub     ecx, 0Ch
0x1c015c2b7  jz      loc_1C01832A6
0x1c015c2bd  sub     ecx, 8
0x1c015c2c0  jz      loc_1C0183298
0x1c015c2c6  cmp     ecx, 2Ch ; ','
0x1c015c2c9  jnz     short loc_1C015C251
0x1c015c2cb  jmp     loc_1C01831BC
0x1c015c2d0  jz      loc_1C0182F83
0x1c015c2d6  mov     eax, 90014h
0x1c015c2db  cmp     ecx, eax
0x1c015c2dd  jbe     loc_1C0182F3C
0x1c015c2e3  sub     ecx, 90018h
0x1c015c2e9  jz      short loc_1C015C352
0x1c015c2eb  sub     ecx, 4
0x1c015c2ee  jnz     short loc_1C015C33C
0x1c015c2f0  mov     rcx, rdi
0x1c015c2f3  call    RefsUnlockVolume
0x1c015c2f8  jmp     loc_1C015C1B5
0x1c015c2fd  mov     eax, 900F4h
0x1c015c302  cmp     ecx, eax
0x1c015c304  ja      loc_1C0183103
0x1c015c30a  jz      loc_1C01830F5
0x1c015c310  mov     eax, 900C4h
0x1c015c315  cmp     ecx, eax
0x1c015c317  ja      loc_1C0183097
0x1c015c31d  jz      loc_1C0183089
0x1c015c323  sub     ecx, 90083h
0x1c015c329  jnz     loc_1C0183035
0x1c015c32f  mov     rcx, rdi
0x1c015c332  call    RefsSetExtendedDasdIo
0x1c015c337  jmp     loc_1C015C1B5
0x1c015c33c  sub     ecx, 4
0x1c015c33f  jnz     loc_1C0182F6C
0x1c015c345  mov     rcx, rdi
0x1c015c348  call    RefsDismountVolume
0x1c015c34d  jmp     loc_1C015C1B5
0x1c015c352  mov     rcx, rdi
0x1c015c355  call    RefsLockVolume
0x1c015c35a  jmp     loc_1C015C1B5
0x1c017e926  push    rbp
0x1c017e928  sub     rsp, 20h
0x1c017e92c  mov     rbp, rdx
0x1c017e92f  cmp     byte ptr [rbp+20h], 0
0x1c017e933  jz      short loc_1C017E951
0x1c017e935  mov     r8, gs:188h; Thread
0x1c017e93e  xor     edx, edx; OutputPriorityInfo
0x1c017e940  lea     rcx, [rbp+28h]; InputPriorityInfo
0x1c017e944  call    cs:__imp_IoApplyPriorityInfoThread
0x1c017e94b  nop     dword ptr [rax+rax+00h]
0x1c017e950  nop
0x1c017e951  add     rsp, 20h
0x1c017e955  pop     rbp
0x1c017e956  retn
0x1c0182f3c  jz      short loc_1C0182F5E
0x1c0182f3e  sub     ecx, 90000h
0x1c0182f44  jz      short loc_1C0182F5E
0x1c0182f46  sub     ecx, 4
0x1c0182f49  jz      short loc_1C0182F5E
0x1c0182f4b  sub     ecx, 4
0x1c0182f4e  jz      short loc_1C0182F5E
0x1c0182f50  sub     ecx, 4
0x1c0182f53  jz      short loc_1C0182F5E
0x1c0182f55  cmp     ecx, 4
0x1c0182f58  jnz     loc_1C015C251
0x1c0182f5e  mov     rcx, rdi
0x1c0182f61  call    RefsOplockRequest
0x1c0182f66  nop
0x1c0182f67  jmp     loc_1C015C1B5
0x1c0182f6c  cmp     ecx, 8
0x1c0182f6f  jnz     loc_1C015C251
0x1c0182f75  mov     rcx, rdi
0x1c0182f78  call    RefsIsVolumeMounted
0x1c0182f7d  nop
0x1c0182f7e  jmp     loc_1C015C1B5
0x1c0182f83  mov     al, cs:RefsStatusDebugEnabled
0x1c0182f89  test    al, al
0x1c0182f8b  jz      short loc_1C0182FA1
0x1c0182f8d  mov     r8d, 642h
0x1c0182f93  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c0182f9a  xor     ecx, ecx; Status
0x1c0182f9c  call    RefsStatusDebug
0x1c0182fa1  xor     ebx, ebx
0x1c0182fa3  xor     r8d, r8d
0x1c0182fa6  mov     rdx, rsi
0x1c0182fa9  mov     rcx, rdi
0x1c0182fac  call    RefsExtendedCompleteRequestInternal
0x1c0182fb1  nop
0x1c0182fb2  jmp     loc_1C015C1B7
0x1c0182fb7  mov     rcx, rdi
0x1c0182fba  cmp     byte ptr [rdx+40h], 0
0x1c0182fbe  jnz     short loc_1C0182FCB
0x1c0182fc0  call    RefsCommonFileSystemControlOnNewStack
0x1c0182fc5  nop
0x1c0182fc6  jmp     loc_1C015C1B5
0x1c0182fcb  call    RefsDefragFile
0x1c0182fd0  nop
0x1c0182fd1  jmp     loc_1C015C1B5
0x1c0182fd6  xor     r8d, r8d
0x1c0182fd9  jmp     short loc_1C0182FE1
0x1c0182fdb  mov     r8d, 1
0x1c0182fe1  mov     rcx, rdi
0x1c0182fe4  call    RefsGetRetrievalPointers
0x1c0182fe9  nop
0x1c0182fea  jmp     loc_1C015C1B5
0x1c0182fef  mov     rcx, rdi
0x1c0182ff2  call    RefsGetVolumeBitmap
0x1c0182ff7  nop
0x1c0182ff8  jmp     loc_1C015C1B5
0x1c0182ffd  mov     rcx, rdi
0x1c0183000  call    RefsGetStatistics
0x1c0183005  nop
0x1c0183006  jmp     loc_1C015C1B5
0x1c018300b  mov     rcx, rdi
0x1c018300e  call    RefsGetCompression
0x1c0183013  nop
0x1c0183014  jmp     loc_1C015C1B5
0x1c0183019  mov     rcx, rdi
0x1c018301c  call    RefsQueryRetrievalPointers
0x1c0183021  nop
0x1c0183022  jmp     loc_1C015C1B5
0x1c0183027  mov     rcx, rdi
0x1c018302a  call    RefsDirtyVolume
0x1c018302f  nop
0x1c0183030  jmp     loc_1C015C1B5
0x1c0183035  sub     ecx, 21h ; '!'
0x1c0183038  jz      short loc_1C018307B
0x1c018303a  sub     ecx, 4
0x1c018303d  jz      short loc_1C018306D
0x1c018303f  sub     ecx, 4
0x1c0183042  jz      short loc_1C018305F
0x1c0183044  cmp     ecx, 0Fh
0x1c0183047  jnz     loc_1C015C251
0x1c018304d  lea     r8d, [rcx-0Eh]
0x1c0183051  mov     rcx, rdi
0x1c0183054  call    RefsReadUsnJournal
0x1c0183059  nop
0x1c018305a  jmp     loc_1C015C1B5
0x1c018305f  mov     rcx, rdi
0x1c0183062  call    RefsDeleteReparsePoint
0x1c0183067  nop
0x1c0183068  jmp     loc_1C015C1B5
0x1c018306d  mov     rcx, rdi
0x1c0183070  call    RefsGetReparsePoint
0x1c0183075  nop
0x1c0183076  jmp     loc_1C015C1B5
0x1c018307b  mov     rcx, rdi; Context1
0x1c018307e  call    RefsSetReparsePoint
0x1c0183083  nop
0x1c0183084  jmp     loc_1C015C1B5
0x1c0183089  mov     rcx, rdi
0x1c018308c  call    RefsSetSparse
0x1c0183091  nop
0x1c0183092  jmp     loc_1C015C1B5
0x1c0183097  sub     ecx, 900E7h
0x1c018309d  jz      short loc_1C01830E7
0x1c018309f  sub     ecx, 4
0x1c01830a2  jz      short loc_1C01830D9
0x1c01830a4  sub     ecx, 4
0x1c01830a7  jz      short loc_1C01830CB
0x1c01830a9  cmp     ecx, 1
0x1c01830ac  jnz     loc_1C015C251
0x1c01830b2  xor     r8d, r8d
0x1c01830b5  jmp     short loc_1C01830BD
0x1c01830b7  mov     r8d, 1
0x1c01830bd  mov     rcx, rdi
0x1c01830c0  call    RefsChangeVolumeSize
0x1c01830c5  nop
0x1c01830c6  jmp     loc_1C015C1B5
0x1c01830cb  mov     rcx, rdi
0x1c01830ce  call    RefsWriteUsnCloseRecord
0x1c01830d3  nop
0x1c01830d4  jmp     loc_1C015C1B5
0x1c01830d9  mov     rcx, rdi
0x1c01830dc  call    RefsReadFileUsnData
0x1c01830e1  nop
0x1c01830e2  jmp     loc_1C015C1B5
0x1c01830e7  mov     rcx, rdi
0x1c01830ea  call    RefsCreateUsnJournal
0x1c01830ef  nop
0x1c01830f0  jmp     loc_1C015C1B5
0x1c01830f5  mov     rcx, rdi
0x1c01830f8  call    RefsQueryUsnJournal
0x1c01830fd  nop
0x1c01830fe  jmp     loc_1C015C1B5
0x1c0183103  sub     ecx, 900F8h
0x1c0183109  jz      loc_1C01831A0
0x1c018310f  sub     ecx, 4
0x1c0183112  jz      short loc_1C0183192
0x1c0183114  sub     ecx, 24h ; '$'
0x1c0183117  jz      short loc_1C0183184
0x1c0183119  sub     ecx, 90h
0x1c018311f  jz      short loc_1C01830B7
0x1c0183121  sub     ecx, 3Ch ; '<'
0x1c0183124  jz      short loc_1C0183176
0x1c0183126  sub     ecx, 18h
0x1c0183129  jz      short loc_1C0183168
0x1c018312b  sub     ecx, 2Ch ; ','
0x1c018312e  jz      short loc_1C018315A
0x1c0183130  sub     ecx, 4
0x1c0183133  jz      short loc_1C018314C
0x1c0183135  cmp     ecx, 4
0x1c0183138  jnz     loc_1C015C251
0x1c018313e  mov     rcx, rdi
0x1c0183141  call    RefsSetPersistentVolumeState
0x1c0183146  nop
0x1c0183147  jmp     loc_1C015C1B5
0x1c018314c  mov     rcx, rdi
0x1c018314f  call    RefsGetRetrievalPointerBase
0x1c0183154  nop
0x1c0183155  jmp     loc_1C015C1B5
  ... truncated ...
```
