# ClfsGetLogFileInformation

- ea: `0x1400699d0`
- end: `0x140069d16`
- name: `ClfsGetLogFileInformation`
- size: `838`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT plfoLog, PCLFS_INFORMATION pinfoBuffer, PULONG pcbInfoBuffer)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14000c2f0`
- `0x14000ed64`
- `0x140011d90`
- `0x140017f20`
- `0x140033ac0`
- `0x140059e80`
- `0x1400699d0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140069a40`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140069a40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140069b7d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007b2cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140069b7d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007b2cc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069bd5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140069bd5`

## pseudocode

```c
NTSTATUS __stdcall ClfsGetLogFileInformation(
        PLOG_FILE_OBJECT plfoLog,
        PCLFS_INFORMATION pinfoBuffer,
        PULONG pcbInfoBuffer)
{
  NTSTATUS v6; // ebx
  __int64 v7; // rsi
  volatile signed __int32 *FsContext2; // r13
  __int64 v10; // [rsp+28h] [rbp-60h]

  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      131,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsGetLogFileInformation",
      97);
  }
  if ( plfoLog && pcbInfoBuffer )
  {
    if ( *pcbInfoBuffer )
    {
      v6 = 0;
      if ( pinfoBuffer )
      {
        KeEnterCriticalRegion();
        v7 = *((_QWORD *)plfoLog->FsContext + 15);
        FsContext2 = (volatile signed __int32 *)plfoLog->FsContext2;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 64LL))(v7);
        CClfsLogCcb::AddRef((CClfsLogCcb *)FsContext2);
        if ( !*(_BYTE *)(*((_QWORD *)FsContext2 + 9) + 74LL) )
          v6 = -1073741790;
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
          {
            WPP_SF_slD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              135,
              (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
              (unsigned int)"ClfsGetLogFileInformation",
              170,
              v6);
          }
        }
        else
        {
          v6 = (*(__int64 (__fastcall **)(__int64, PLOG_FILE_OBJECT, _QWORD, _QWORD, _DWORD, PCLFS_INFORMATION, PULONG))(*(_QWORD *)v7 + 240LL))(
                 v7,
                 plfoLog,
                 0,
                 0,
                 0,
                 pinfoBuffer,
                 pcbInfoBuffer);
          if ( v6 < 0
            && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
          {
            LODWORD(v10) = v6;
            WPP_SF_slD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              136,
              (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
              (unsigned int)"ClfsGetLogFileInformation",
              197,
              v10);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 72LL))(v7);
        if ( _InterlockedExchangeAdd(FsContext2 + 6, 0xFFFFFFFF) == 1 )
        {
          CClfsLogCcb::~CClfsLogCcb((CClfsLogCcb *)FsContext2);
          ExFreeToNPagedLookasideList(&CClfsLogCcb::m_laList, (PVOID)FsContext2);
        }
        KeLeaveCriticalRegion();
        if ( v6 >= 0
          && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            137,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsGetLogFileInformation",
            233);
        }
        return v6;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            134,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsGetLogFileInformation",
            131,
            -1073741592);
        }
        return -1073741592;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          133,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsGetLogFileInformation",
          116,
          -1073741306);
      }
      return -1073741306;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        132,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsGetLogFileInformation",
        105,
        -1073741811);
    }
    return -1073741811;
  }
}

```

## disassembly

```asm
0x1400699d0  mov     [rsp+arg_8], rbx
0x1400699d5  mov     [rsp+arg_10], rsi
0x1400699da  push    rdi
0x1400699db  push    r12
0x1400699dd  push    r13
0x1400699df  push    r14
0x1400699e1  push    r15
0x1400699e3  sub     rsp, 60h
0x1400699e7  mov     rdi, r8
0x1400699ea  mov     r15, rdx
0x1400699ed  mov     r14, rcx
0x1400699f0  lea     r12, WPP_GLOBAL_Control
0x1400699f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400699fe  cmp     rcx, r12
0x140069a01  jz      short loc_140069A10
0x140069a03  mov     eax, [rcx+2Ch]
0x140069a06  bt      eax, 1Ah
0x140069a0a  jb      loc_140069BE3
0x140069a10  test    r14, r14
0x140069a13  jz      loc_140069CCB
0x140069a19  test    rdi, rdi
0x140069a1c  jz      loc_140069CCB
0x140069a22  cmp     dword ptr [rdi], 0
0x140069a25  jz      loc_140069C0C
0x140069a2b  xor     ebx, ebx
0x140069a2d  mov     [rsp+88h+var_38], rbx
0x140069a32  mov     [rsp+88h+var_40], rbx
0x140069a37  test    r15, r15
0x140069a3a  jz      loc_140069C57
0x140069a40  call    cs:__imp_KeEnterCriticalRegion
0x140069a47  nop     dword ptr [rax+rax+00h]
0x140069a4c  mov     rax, [r14+18h]
0x140069a50  mov     rsi, [rax+78h]
0x140069a54  mov     [rsp+88h+arg_0], rsi
0x140069a5c  mov     [rsp+88h+var_38], rsi
0x140069a61  mov     r13, [r14+20h]
0x140069a65  mov     [rsp+88h+var_40], r13
0x140069a6a  mov     rax, [rsi]
0x140069a6d  mov     rax, [rax+40h]
0x140069a71  mov     rcx, rsi
0x140069a74  call    _guard_dispatch_icall
0x140069a79  mov     rcx, r13; this
0x140069a7c  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x140069a81  mov     [rsp+88h+var_44], ebx
0x140069a85  mov     rax, [r13+48h]
0x140069a89  mov     ecx, 0C0000022h
0x140069a8e  cmp     [rax+4Ah], bl
0x140069a91  cmovz   ebx, ecx
0x140069a94  mov     [rsp+88h+var_44], ebx
0x140069a98  mov     [rsp+88h+var_48], ebx
0x140069a9c  test    ebx, ebx
0x140069a9e  js      loc_140069B52
0x140069aa4  mov     rax, [rsi]
0x140069aa7  mov     rax, [rax+0F0h]
0x140069aae  mov     [rsp+88h+var_58], rdi
0x140069ab3  mov     [rsp+88h+var_60], r15
0x140069ab8  mov     [rsp+88h+var_68], 0
0x140069ac0  xor     r9d, r9d
0x140069ac3  xor     r8d, r8d
0x140069ac6  mov     rdx, r14
0x140069ac9  mov     rcx, rsi
0x140069acc  call    _guard_dispatch_icall
0x140069ad1  mov     ebx, eax
0x140069ad3  mov     [rsp+88h+var_48], eax
0x140069ad7  jmp     short loc_140069AF3
0x140069ad9  mov     ebx, eax
0x140069adb  mov     [rsp+88h+var_48], eax
0x140069adf  lea     r12, WPP_GLOBAL_Control
0x140069ae6  mov     r13, [rsp+88h+var_40]
0x140069aeb  mov     rsi, [rsp+88h+arg_0]
0x140069af3  test    ebx, ebx
0x140069af5  jns     short loc_140069B5E
0x140069af7  mov     rcx, cs:WPP_GLOBAL_Control
0x140069afe  cmp     rcx, r12
0x140069b01  jz      short loc_140069B5E
0x140069b03  mov     eax, [rcx+2Ch]
0x140069b06  bt      eax, 1Ah
0x140069b0a  jnb     short loc_140069B5E
0x140069b0c  mov     edx, 88h
0x140069b11  mov     dword ptr [rsp+88h+var_60], ebx
0x140069b15  mov     [rsp+88h+var_68], 0FC5h
0x140069b1d  jmp     short loc_140069B39
0x140069b1f  mov     eax, [rcx+2Ch]
0x140069b22  bt      eax, 1Ah
0x140069b26  jnb     short loc_140069B5E
0x140069b28  mov     edx, 87h
0x140069b2d  mov     dword ptr [rsp+88h+var_60], ebx
0x140069b31  mov     [rsp+88h+var_68], 0FAAh
0x140069b39  lea     r9, aClfsgetlogfile; "ClfsGetLogFileInformation"
0x140069b40  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140069b47  mov     rcx, [rcx+18h]
0x140069b4b  call    WPP_SF_slD
0x140069b50  jmp     short loc_140069B5E
0x140069b52  mov     rcx, cs:WPP_GLOBAL_Control
0x140069b59  cmp     rcx, r12
0x140069b5c  jnz     short loc_140069B1F
0x140069b5e  mov     rax, [rsi]
0x140069b61  mov     rax, [rax+48h]
0x140069b65  mov     rcx, rsi
0x140069b68  call    _guard_dispatch_icall
0x140069b6d  mov     eax, 0FFFFFFFFh
0x140069b72  lock xadd [r13+18h], eax
0x140069b78  cmp     eax, 1
0x140069b7b  jz      short loc_140069BC3
0x140069b7d  call    cs:__imp_KeLeaveCriticalRegion
0x140069b84  nop     dword ptr [rax+rax+00h]
0x140069b89  test    ebx, ebx
0x140069b8b  js      short loc_140069BA6
0x140069b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140069b94  cmp     rcx, r12
0x140069b97  jz      short loc_140069BA6
0x140069b99  test    dword ptr [rcx+2Ch], 4000000h
0x140069ba0  jnz     loc_140069CA2
0x140069ba6  mov     eax, ebx
0x140069ba8  lea     r11, [rsp+88h+var_28]
0x140069bad  mov     rbx, [r11+38h]
0x140069bb1  mov     rsi, [r11+40h]
0x140069bb5  mov     rsp, r11
0x140069bb8  pop     r15
0x140069bba  pop     r14
0x140069bbc  pop     r13
0x140069bbe  pop     r12
0x140069bc0  pop     rdi
0x140069bc1  retn
0x140069bc3  mov     rcx, r13; this
0x140069bc6  call    ??1CClfsLogCcb@@QEAA@XZ; CClfsLogCcb::~CClfsLogCcb(void)
0x140069bcb  mov     rdx, r13; Entry
0x140069bce  lea     rcx, ?m_laList@CClfsLogCcb@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140069bd5  call    cs:__imp_ExFreeToNPagedLookasideList
0x140069bdc  nop     dword ptr [rax+rax+00h]
0x140069be1  jmp     short loc_140069B7D
0x140069be3  mov     edx, 83h
0x140069be8  mov     [rsp+88h+var_68], 0F61h
0x140069bf0  lea     r9, aClfsgetlogfile; "ClfsGetLogFileInformation"
0x140069bf7  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140069bfe  mov     rcx, [rcx+18h]
0x140069c02  call    WPP_SF_sd
0x140069c07  jmp     loc_140069A10
0x140069c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140069c13  cmp     rcx, r12
0x140069c16  jz      short loc_140069C4D
0x140069c18  test    dword ptr [rcx+2Ch], 4000000h
0x140069c1f  jz      short loc_140069C4D
0x140069c21  mov     edx, 85h
0x140069c26  mov     dword ptr [rsp+88h+var_60], 0C0000206h
0x140069c2e  mov     [rsp+88h+var_68], 0F74h
0x140069c36  lea     r9, aClfsgetlogfile; "ClfsGetLogFileInformation"
0x140069c3d  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140069c44  mov     rcx, [rcx+18h]
0x140069c48  call    WPP_SF_slD
0x140069c4d  mov     eax, 0C0000206h
0x140069c52  jmp     loc_140069BA8
0x140069c57  mov     rcx, cs:WPP_GLOBAL_Control
0x140069c5e  cmp     rcx, r12
0x140069c61  jz      short loc_140069C98
0x140069c63  test    dword ptr [rcx+2Ch], 4000000h
0x140069c6a  jz      short loc_140069C98
0x140069c6c  mov     edx, 86h
0x140069c71  mov     dword ptr [rsp+88h+var_60], 0C00000E8h
0x140069c79  mov     [rsp+88h+var_68], 0F83h
0x140069c81  lea     r9, aClfsgetlogfile; "ClfsGetLogFileInformation"
0x140069c88  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140069c8f  mov     rcx, [rcx+18h]
0x140069c93  call    WPP_SF_slD
0x140069c98  mov     eax, 0C00000E8h
0x140069c9d  jmp     loc_140069BA8
0x140069ca2  mov     edx, 89h
0x140069ca7  mov     [rsp+88h+var_68], 0FE9h
0x140069caf  lea     r9, aClfsgetlogfile; "ClfsGetLogFileInformation"
0x140069cb6  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140069cbd  mov     rcx, [rcx+18h]
0x140069cc1  call    WPP_SF_sd
0x140069cc6  jmp     loc_140069BA6
0x140069ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x140069cd2  cmp     rcx, r12
0x140069cd5  jz      short loc_140069D0C
0x140069cd7  test    dword ptr [rcx+2Ch], 4000000h
0x140069cde  jz      short loc_140069D0C
0x140069ce0  mov     edx, 84h
0x140069ce5  mov     dword ptr [rsp+88h+var_60], 0C000000Dh
0x140069ced  mov     [rsp+88h+var_68], 0F69h
0x140069cf5  lea     r9, aClfsgetlogfile; "ClfsGetLogFileInformation"
0x140069cfc  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140069d03  mov     rcx, [rcx+18h]
0x140069d07  call    WPP_SF_slD
0x140069d0c  mov     eax, 0C000000Dh
0x140069d11  jmp     loc_140069BA8
0x14007b290  push    rbp
0x14007b292  sub     rsp, 40h
0x14007b296  mov     rbp, rdx
0x14007b299  mov     rcx, [rbp+50h]
0x14007b29d  test    rcx, rcx
0x14007b2a0  jz      short loc_14007B2B6
0x14007b2a2  mov     rax, [rcx]
0x14007b2a5  mov     rax, [rax+48h]
0x14007b2a9  call    _guard_dispatch_icall
0x14007b2ae  mov     qword ptr [rbp+50h], 0
0x14007b2b6  mov     rcx, [rbp+48h]; Entry
0x14007b2ba  test    rcx, rcx
0x14007b2bd  jz      short loc_14007B2CC
0x14007b2bf  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007b2c4  mov     qword ptr [rbp+48h], 0
0x14007b2cc  call    cs:__imp_KeLeaveCriticalRegion
0x14007b2d3  nop     dword ptr [rax+rax+00h]
0x14007b2d8  nop
0x14007b2d9  add     rsp, 40h
0x14007b2dd  pop     rbp
0x14007b2de  retn
```
