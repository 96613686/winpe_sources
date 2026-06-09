# FatOpenExistingDirectory

- ea: `0x14002aae8`
- end: `0x14002ade5`
- name: `FatOpenExistingDirectory`
- size: `765`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1400268c0`

## callees

- `0x140002ed8`
- `0x1400201f4`
- `0x14002aae8`
- `0x1400364fc`
- `0x14003db44`
- `0x1400475e8`
- `0x14004763c`
- `0x14004814c`
- `0x140048184`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002ac21`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002ac21`
- `ntoskrnl!IoSetShareAccess` at `0x14002ac8e`
- `ntoskrnl!IoSetShareAccess` at `0x14002ac8e`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002ac52`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002ac52`
- `ntoskrnl!ExRaiseStatus` at `0x14002ac69`
- `ntoskrnl!ExRaiseStatus` at `0x14002ad95`
- `ntoskrnl!ExRaiseStatus` at `0x14002ac69`
- `ntoskrnl!ExRaiseStatus` at `0x14002ad95`

## pseudocode

```c
__int64 __fastcall FatOpenExistingDirectory(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PVOID **a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10,
        __int64 a11,
        ACCESS_MASK *a12,
        unsigned __int16 a13,
        int a14,
        char a15,
        __int64 a16,
        char a17,
        char a18)
{
  __int64 v22; // rdx
  union _LARGE_INTEGER v23; // rcx
  NTSTATUS v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  NTSTATUS Callback; // eax
  __int64 Ccb; // [rsp+68h] [rbp-30h]
  PVOID *Dcb; // [rsp+A0h] [rbp+8h]

  *(_OWORD *)a1 = 0;
  if ( a15 && *(_BYTE *)(a5 + 376) != 32 )
    FatGetNeedEaCount(a2, a5);
  if ( ((a14 - 1) & 0xFFFFFFFD) != 0 )
  {
    *(_DWORD *)a1 = -1073741771;
    return a1;
  }
  v22 = a8;
  LOBYTE(v22) = *(_BYTE *)(a8 + 11);
  if ( (unsigned __int8)FatCheckFileAccess(a1, v22, a12) )
  {
    Dcb = (PVOID *)FatCreateDcb(v23, a5, a7, a9, a10, a8, a11);
    *a6 = Dcb;
    v24 = FsRtlCheckOplockEx(Dcb + 11, *(PIRP *)(a2 + 40), 2u, 0, 0, 0);
    *(_DWORD *)a1 = v24;
    if ( a18 )
    {
      if ( v24 )
        goto LABEL_12;
      v24 = FsRtlOplockFsctrl(*a6 + 11, *(PIRP *)(a2 + 40), *((_DWORD *)*a6 + 57) + 1);
      *(_DWORD *)a1 = v24;
    }
    if ( v24 )
    {
LABEL_12:
      *(_DWORD *)(a2 + 72) = v24;
      ExRaiseStatus(v24);
    }
    IoSetShareAccess(*a12, a13, (PFILE_OBJECT)a4, (PSHARE_ACCESS)(*a6 + 25));
    Ccb = FatCreateCcb(v26, v25);
    FatSetFileObject(a4, v27, *a6, Ccb);
    ++*((_DWORD *)*a6 + 57);
    ++*((_DWORD *)*a6 + 58);
    ++*(_DWORD *)(a5 + 272);
    if ( !*(_WORD *)(a4 + 75) )
      ++*(_DWORD *)(a5 + 276);
    if ( (*(_DWORD *)(a5 + 200) & 0x400000) != 0 )
    {
      if ( *a6 )
      {
        if ( ((_DWORD)(*a6)[24] & 0x60000) != 0 )
        {
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) |= *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL)
                                                                                  + 16LL);
          if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) & 0x27) != 0 )
          {
            *(_DWORD *)(a2 + 136) = 131080;
            Callback = EfsFileCreateCallback(
                         (unsigned int)*a6,
                         a7,
                         a3,
                         *(_DWORD *)(a2 + 136),
                         (*(_DWORD *)(a5 + 200) >> 14) & 1,
                         a2,
                         a5 - 416);
            if ( Callback < 0 )
            {
              *(_DWORD *)a1 = Callback;
              *(_DWORD *)(a2 + 72) = Callback;
              ExRaiseStatus(Callback);
            }
            *(_DWORD *)(a2 + 68) |= 0x8000u;
          }
        }
      }
    }
    *(_DWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 1;
    if ( a17 )
      *(_DWORD *)(*(_QWORD *)(a4 + 32) + 4LL) |= 0x800u;
  }
  else
  {
    *(_DWORD *)a1 = -1073741790;
  }
  return a1;
}

```

## disassembly

```asm
0x14002aae8  mov     rax, rsp
0x14002aaeb  mov     [rax+10h], rbx
0x14002aaef  mov     [rax+18h], rsi
0x14002aaf3  mov     [rax+20h], r9
0x14002aaf7  push    rdi
0x14002aaf8  push    r12
0x14002aafa  push    r13
0x14002aafc  push    r14
0x14002aafe  push    r15
0x14002ab00  sub     rsp, 70h
0x14002ab04  mov     r15, r9
0x14002ab07  mov     r13, r8
0x14002ab0a  mov     rdi, rdx
0x14002ab0d  mov     rbx, rcx
0x14002ab10  xorps   xmm0, xmm0
0x14002ab13  movups  xmmword ptr [rcx], xmm0
0x14002ab16  xor     r14d, r14d
0x14002ab19  mov     [rax+8], r14
0x14002ab1d  mov     [rax-30h], r14
0x14002ab21  mov     [rax-38h], r14b
0x14002ab25  mov     rsi, [rsp+98h+arg_20]
0x14002ab2d  cmp     [rsp+98h+arg_70], r14b
0x14002ab35  jz      short loc_14002AB76
0x14002ab37  cmp     byte ptr [rsi+178h], 20h ; ' '
0x14002ab3e  jz      short loc_14002AB76
0x14002ab40  mov     [rax+80h], r14d
0x14002ab47  lea     r9, [rax+80h]
0x14002ab4e  mov     r8, [rsp+98h+arg_38]
0x14002ab56  mov     rdx, rsi; int
0x14002ab59  mov     rcx, rdi; int
0x14002ab5c  call    FatGetNeedEaCount
0x14002ab61  cmp     [rsp+98h+arg_78], r14d
0x14002ab69  jz      short loc_14002AB76
0x14002ab6b  mov     dword ptr [rbx], 0C0000022h
0x14002ab71  jmp     loc_14002ADC7
0x14002ab76  mov     eax, [rsp+98h+arg_68]
0x14002ab7d  dec     eax
0x14002ab7f  test    eax, 0FFFFFFFDh
0x14002ab84  jz      short loc_14002AB91
0x14002ab86  mov     dword ptr [rbx], 0C0000035h
0x14002ab8c  jmp     loc_14002ADC7
0x14002ab91  mov     r12, [rsp+98h+arg_58]
0x14002ab99  mov     r8, r12
0x14002ab9c  mov     rdx, [rsp+98h+arg_38]
0x14002aba4  mov     dl, [rdx+0Bh]
0x14002aba7  call    FatCheckFileAccess
0x14002abac  test    al, al
0x14002abae  jz      short loc_14002AB6B
0x14002abb0  mov     rax, [rsp+98h+arg_50]
0x14002abb8  mov     [rsp+98h+var_68], rax
0x14002abbd  mov     rax, [rsp+98h+arg_38]
0x14002abc5  mov     [rsp+98h+PostIrpRoutine], rax
0x14002abca  mov     eax, [rsp+98h+arg_48]
0x14002abd1  mov     dword ptr [rsp+98h+CompletionRoutine], eax
0x14002abd5  mov     r9d, [rsp+98h+arg_40]
0x14002abdd  mov     r8, [rsp+98h+arg_30]
0x14002abe5  mov     rdx, rsi
0x14002abe8  call    FatCreateDcb
0x14002abed  mov     [rsp+98h+arg_0], rax
0x14002abf5  mov     r14, [rsp+98h+arg_28]
0x14002abfd  mov     [r14], rax
0x14002ac00  lea     rcx, [rax+58h]; Oplock
0x14002ac04  mov     [rsp+98h+PostIrpRoutine], 0; PostIrpRoutine
0x14002ac0d  mov     [rsp+98h+CompletionRoutine], 0; CompletionRoutine
0x14002ac16  xor     r9d, r9d; Context
0x14002ac19  lea     r8d, [r9+2]; Flags
0x14002ac1d  mov     rdx, [rdi+28h]; Irp
0x14002ac21  call    cs:__imp_FsRtlCheckOplockEx
0x14002ac28  nop     dword ptr [rax+rax+00h]
0x14002ac2d  mov     [rbx], eax
0x14002ac2f  cmp     [rsp+98h+arg_88], 0
0x14002ac37  jz      short loc_14002AC60
0x14002ac39  test    eax, eax
0x14002ac3b  jnz     short loc_14002AC64
0x14002ac3d  mov     rcx, [r14]
0x14002ac40  mov     r8d, [rcx+0E4h]
0x14002ac47  inc     r8d; OpenCount
0x14002ac4a  add     rcx, 58h ; 'X'; Oplock
0x14002ac4e  mov     rdx, [rdi+28h]; Irp
0x14002ac52  call    cs:__imp_FsRtlOplockFsctrl
0x14002ac59  nop     dword ptr [rax+rax+00h]
0x14002ac5e  mov     [rbx], eax
0x14002ac60  test    eax, eax
0x14002ac62  jz      short loc_14002AC75
0x14002ac64  mov     [rdi+48h], eax
0x14002ac67  mov     ecx, eax; Status
0x14002ac69  call    cs:__imp_ExRaiseStatus
0x14002ac75  mov     r9, [r14]
0x14002ac78  add     r9, 0C8h; ShareAccess
0x14002ac7f  movzx   edx, [rsp+98h+arg_60]; DesiredShareAccess
0x14002ac87  mov     r8, r15; FileObject
0x14002ac8a  mov     ecx, [r12]; DesiredAccess
0x14002ac8e  call    cs:__imp_IoSetShareAccess
0x14002ac95  nop     dword ptr [rax+rax+00h]
0x14002ac9a  call    FatCreateCcb
0x14002ac9f  mov     [rsp+98h+var_30], rax
0x14002aca4  mov     r9, rax
0x14002aca7  mov     r8, [r14]
0x14002acaa  mov     rcx, r15
0x14002acad  call    FatSetFileObject
0x14002acb2  mov     r8, [r14]
0x14002acb5  inc     dword ptr [r8+0E4h]
0x14002acbc  mov     rax, [r14]
0x14002acbf  inc     dword ptr [rax+0E8h]
0x14002acc5  inc     dword ptr [rsi+110h]
0x14002accb  mov     al, [r15+4Ch]
0x14002accf  or      al, [r15+4Bh]
0x14002acd3  jnz     short loc_14002ACDB
0x14002acd5  inc     dword ptr [rsi+114h]
0x14002acdb  mov     [rsp+98h+var_38], 1
0x14002ace0  mov     eax, [rsi+0C8h]
0x14002ace6  bt      eax, 16h
0x14002acea  jnb     loc_14002ADA6
0x14002acf0  mov     rax, [r14]
0x14002acf3  test    rax, rax
0x14002acf6  jz      loc_14002ADA6
0x14002acfc  test    dword ptr [rax+0C0h], 60000h
0x14002ad06  jz      loc_14002ADA6
0x14002ad0c  mov     rax, [r13+8]
0x14002ad10  mov     rcx, [rax+8]
0x14002ad14  mov     eax, [rcx+10h]
0x14002ad17  or      [rcx+14h], eax
0x14002ad1a  mov     rax, [r13+8]
0x14002ad1e  mov     rcx, [rax+8]
0x14002ad22  mov     eax, [rcx+14h]
0x14002ad25  test    al, 27h
0x14002ad27  jz      short loc_14002ADA6
0x14002ad29  mov     dword ptr [rdi+88h], 20008h
0x14002ad33  mov     r10d, [rsi+0C8h]
0x14002ad3a  mov     rcx, [r14]
0x14002ad3d  lea     rax, [rdi+80h]
0x14002ad44  lea     r8, [rcx+90h]
0x14002ad4b  lea     r9, [rsi-1A0h]
0x14002ad52  shr     r10d, 0Eh
0x14002ad56  and     r10d, 1
0x14002ad5a  mov     [rsp+98h+var_50], rax
0x14002ad5f  mov     [rsp+98h+var_58], r8
0x14002ad64  mov     [rsp+98h+var_68], r9
0x14002ad69  mov     [rsp+98h+PostIrpRoutine], rdi
0x14002ad6e  mov     dword ptr [rsp+98h+CompletionRoutine], r10d
0x14002ad73  mov     r9d, [rdi+88h]
0x14002ad7a  mov     r8, r13
0x14002ad7d  mov     rdx, [rsp+98h+arg_30]
0x14002ad85  call    EfsFileCreateCallback
0x14002ad8a  test    eax, eax
0x14002ad8c  jns     short loc_14002ADA1
0x14002ad8e  mov     [rbx], eax
0x14002ad90  mov     [rdi+48h], eax
0x14002ad93  mov     ecx, eax; Status
0x14002ad95  call    cs:__imp_ExRaiseStatus
0x14002ada1  bts     dword ptr [rdi+44h], 0Fh
0x14002ada6  mov     dword ptr [rbx], 0
0x14002adac  mov     qword ptr [rbx+8], 1
0x14002adb4  cmp     [rsp+98h+arg_80], 0
0x14002adbc  jz      short loc_14002ADC7
0x14002adbe  mov     rax, [r15+20h]
0x14002adc2  bts     dword ptr [rax+4], 0Bh
0x14002adc7  mov     rax, rbx
0x14002adca  lea     r11, [rsp+98h+var_28]
0x14002adcf  mov     rbx, [r11+38h]
0x14002add3  mov     rsi, [r11+40h]
0x14002add7  mov     rsp, r11
0x14002adda  pop     r15
0x14002addc  pop     r14
0x14002adde  pop     r13
0x14002ade0  pop     r12
0x14002ade2  pop     rdi
0x14002ade3  retn
0x14005c6a2  push    rbp
0x14005c6a4  sub     rsp, 60h
0x14005c6a8  mov     rbp, rdx
0x14005c6ab  movzx   eax, cl
0x14005c6ae  test    cl, cl
0x14005c6b0  jz      loc_14005C764
0x14005c6b6  cmp     byte ptr [rbp+60h], 0
0x14005c6ba  jz      short loc_14005C70B
0x14005c6bc  mov     rdx, [rbp+0C8h]
0x14005c6c3  mov     rax, [rdx]
0x14005c6c6  mov     ecx, [rax+0E4h]
0x14005c6cc  dec     ecx
0x14005c6ce  mov     [rax+0E4h], ecx
0x14005c6d4  mov     rax, [rdx]
0x14005c6d7  mov     ecx, [rax+0E8h]
0x14005c6dd  dec     ecx
0x14005c6df  mov     [rax+0E8h], ecx
0x14005c6e5  mov     r8, [rbp+0C0h]
0x14005c6ec  dec     dword ptr [r8+110h]
0x14005c6f3  mov     rdx, [rbp+0B8h]
0x14005c6fa  mov     al, [rdx+4Ch]
0x14005c6fd  or      al, [rdx+4Bh]
0x14005c700  jnz     short loc_14005C712
0x14005c702  dec     dword ptr [r8+114h]
0x14005c709  jmp     short loc_14005C712
0x14005c70b  mov     rdx, [rbp+0B8h]
0x14005c712  mov     rax, [rbp+0A0h]
0x14005c719  test    rax, rax
0x14005c71c  jz      short loc_14005C753
0x14005c71e  test    rdx, rdx
0x14005c721  jz      short loc_14005C739
0x14005c723  mov     qword ptr [rdx+28h], 0
0x14005c72b  cmp     [rdx+18h], rax
0x14005c72f  jnz     short loc_14005C739
0x14005c731  mov     qword ptr [rdx+18h], 0
0x14005c739  lea     rdx, [rbp+0A0h]
0x14005c740  call    FatDeleteFcb
0x14005c745  mov     rax, [rbp+0C8h]
0x14005c74c  mov     qword ptr [rax], 0
0x14005c753  cmp     qword ptr [rbp+68h], 0
0x14005c758  jz      short loc_14005C764
0x14005c75a  lea     rdx, [rbp+68h]
0x14005c75e  call    FatDeleteCcb
0x14005c763  nop
0x14005c764  add     rsp, 60h
0x14005c768  pop     rbp
0x14005c769  retn
```
