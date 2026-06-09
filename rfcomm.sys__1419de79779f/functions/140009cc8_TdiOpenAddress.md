# TdiOpenAddress

- ea: `0x140009cc8`
- end: `0x14000a058`
- name: `TdiOpenAddress`
- size: `912`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007d40`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140008104`
- `0x140009cc8`
- `0x14000b888`
- `0x14001e74c`
- `0x14001ea34`
- `0x140033edc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009e66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009e66`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009f9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009f9c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009d90`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009d90`

## string_xrefs

- `0x140009f23`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140009f3f`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140009fb7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiOpenAddress(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, unsigned __int16 a5)
{
  __int64 v6; // rdi
  __int64 v7; // rbx
  int v8; // edx
  int Address; // eax
  int v11; // edx
  __int64 v12; // r12
  int v13; // r15d
  int v14; // edx
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rcx
  _QWORD v18[9]; // [rsp+40h] [rbp-48h] BYREF

  *a3 = 0;
  if ( a5 < 0x27u || *(_DWORD *)a4 != 1 || *(_WORD *)(a4 + 4) != 28 || *(_WORD *)(a4 + 6) != 32 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        54,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    return 3221225991LL;
  }
  v6 = a4 + 8;
  v7 = *(unsigned int *)(a4 + 32);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DDd(WPP_GLOBAL_Control->DeviceExtension, a2, (_DWORD)a3, 55);
  if ( (unsigned int)(v7 - 1) > 0xFFFFFFFD )
    goto LABEL_17;
  if ( (unsigned int)(v7 - 1) > 0x1D )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        56,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        v7);
    return 3221225991LL;
  }
  if ( *(_BYTE *)(a1 + 16 * v7 + 136)
    && (KeGetCurrentIrql() >= 2u || !IsCallingProcess(*(PSECURITY_DESCRIPTOR *)(a1 + 16 * (v7 + 9)), 1)) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        15,
        57,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        v7);
    return 3221225506LL;
  }
LABEL_17:
  v18[0] = 0;
  Address = TdiCreateAddress(a1, v6, v18);
  v12 = v18[0];
  v13 = Address;
  if ( Address >= 0 )
  {
    *(_BYTE *)(a1 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
    if ( (_DWORD)v7 )
    {
      if ( (_DWORD)v7 == -1 )
      {
        LODWORD(v7) = 1;
        while ( 1 )
        {
          if ( !*(_BYTE *)(a1 + 16LL * (unsigned int)v7 + 136) )
          {
            v16 = *(_DWORD *)(a1 + 92);
            if ( !_bittest(&v16, v7) )
              break;
          }
          LODWORD(v7) = v7 + 1;
          if ( (unsigned int)v7 > 0x1E )
          {
            v13 = -1073741303;
            goto LABEL_34;
          }
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            15,
            58,
            (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
            v7);
      }
      else
      {
        v15 = *(_DWORD *)(a1 + 92);
        if ( _bittest(&v15, v7) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v14,
              15,
              59,
              (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
              v7);
          v13 = -1073741757;
LABEL_34:
          KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
          if ( v13 < 0 )
            RefObj_ReleaseEx(
              v12 + 24,
              1414090313,
              1511,
              "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
          goto LABEL_36;
        }
      }
    }
    RefObj_AddRefEx(a1 + 24, 1380205633, 1493, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    *(_QWORD *)(v12 + 64) = a1;
    RefObj_AddRefEx(v12 + 24, 541672532, 1495, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    v17 = *(_QWORD **)(a1 + 120);
    if ( *v17 != a1 + 112 )
      __fastfail(3u);
    *(_QWORD *)v12 = a1 + 112;
    *(_QWORD *)(v12 + 8) = v17;
    *v17 = v12;
    *(_QWORD *)(a1 + 120) = v12;
    *(_DWORD *)(v12 + 112) = v7;
    *(_DWORD *)(a1 + 92) |= 1 << v7;
    *(_QWORD *)(v12 + 72) = a2;
    goto LABEL_34;
  }
LABEL_36:
  *a3 = v12;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      15,
      60,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140009cc8  mov     [rsp+arg_0], rbx
0x140009ccd  mov     [rsp+arg_10], r8
0x140009cd2  mov     [rsp+arg_8], rdx
0x140009cd7  push    rbp
0x140009cd8  push    rsi
0x140009cd9  push    rdi
0x140009cda  push    r12
0x140009cdc  push    r13
0x140009cde  push    r14
0x140009ce0  push    r15
0x140009ce2  sub     rsp, 50h
0x140009ce6  xor     r12d, r12d
0x140009ce9  mov     rbp, rcx
0x140009cec  cmp     [rsp+88h+arg_20], 27h ; '''
0x140009cf5  mov     [r8], r12
0x140009cf8  lea     r14d, [r12+1]
0x140009cfd  jb      loc_14000A005
0x140009d03  cmp     [r9], r14d
0x140009d06  jnz     loc_14000A005
0x140009d0c  cmp     word ptr [r9+4], 1Ch
0x140009d12  jnz     loc_14000A005
0x140009d18  cmp     word ptr [r9+6], 20h ; ' '
0x140009d1e  jnz     loc_14000A005
0x140009d24  lea     rdi, [r9+8]
0x140009d28  mov     ebx, [rdi+18h]
0x140009d2b  lea     rsi, WPP_RECORDER_INITIALIZED
0x140009d32  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009d39  jz      short loc_140009D68
0x140009d3b  mov     rax, [rdi]
0x140009d3e  lea     r9d, [r12+37h]
0x140009d43  shr     rax, 20h
0x140009d47  movzx   ecx, ax
0x140009d4a  mov     eax, [rdi]
0x140009d4c  mov     [rsp+88h+var_50], ebx
0x140009d50  mov     [rsp+88h+var_58], eax
0x140009d54  mov     [rsp+88h+var_60], ecx
0x140009d58  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d5f  mov     rcx, [rcx+40h]
0x140009d63  call    WPP_RECORDER_SF_DDd
0x140009d68  lea     eax, [rbx-1]
0x140009d6b  cmp     eax, 0FFFFFFFDh
0x140009d6e  ja      loc_140009E30
0x140009d74  lea     eax, [rbx-1]
0x140009d77  cmp     eax, 1Dh
0x140009d7a  ja      short loc_140009DF5
0x140009d7c  mov     rax, rbx
0x140009d7f  add     rax, rax
0x140009d82  cmp     [rbp+rax*8+88h], r12b
0x140009d8a  jz      loc_140009E30
0x140009d90  call    cs:__imp_KeGetCurrentIrql
0x140009d97  nop     dword ptr [rax+rax+00h]
0x140009d9c  cmp     al, 2
0x140009d9e  jnb     short loc_140009DB8
0x140009da0  lea     rcx, [rbx+9]
0x140009da4  mov     dl, r14b
0x140009da7  add     rcx, rcx
0x140009daa  mov     rcx, [rbp+rcx*8+0]; SecurityDescriptor
0x140009daf  call    IsCallingProcess
0x140009db4  test    al, al
0x140009db6  jnz     short loc_140009E30
0x140009db8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009dbf  jz      short loc_140009DEB
0x140009dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140009dc8  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140009dcf  mov     r9d, 39h ; '9'
0x140009dd5  mov     [rsp+88h+var_60], ebx
0x140009dd9  mov     [rsp+88h+var_68], rdi
0x140009dde  mov     rcx, [rcx+40h]
0x140009de2  lea     r8d, [r9-2Ah]
0x140009de6  call    WPP_RECORDER_SF_d
0x140009deb  mov     eax, 0C0000022h
0x140009df0  jmp     loc_14000A03F
0x140009df5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009dfc  jz      loc_14000A03A
0x140009e02  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e09  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140009e10  mov     r9d, 38h ; '8'
0x140009e16  mov     [rsp+88h+var_60], ebx
0x140009e1a  mov     r8d, r14d
0x140009e1d  mov     [rsp+88h+var_68], rdi
0x140009e22  mov     rcx, [rcx+40h]
0x140009e26  call    WPP_RECORDER_SF_d
0x140009e2b  jmp     loc_14000A03A
0x140009e30  lea     r8, [rsp+88h+var_48]
0x140009e35  mov     [rsp+88h+var_48], r12
0x140009e3a  mov     rdx, rdi
0x140009e3d  mov     rcx, rbp
0x140009e40  call    TdiCreateAddress
0x140009e45  mov     r12, [rsp+88h+var_48]
0x140009e4a  mov     r15d, eax
0x140009e4d  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140009e54  mov     r13d, 0Fh
0x140009e5a  test    eax, eax
0x140009e5c  js      loc_140009FC9
0x140009e62  lea     rcx, [rbp+30h]; SpinLock
0x140009e66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009e6d  nop     dword ptr [rax+rax+00h]
0x140009e72  mov     [rbp+38h], al
0x140009e75  test    ebx, ebx
0x140009e77  jz      loc_140009F1A
0x140009e7d  cmp     ebx, 0FFFFFFFFh
0x140009e80  jz      short loc_140009EC2
0x140009e82  mov     eax, [rbp+5Ch]
0x140009e85  bt      eax, ebx
0x140009e88  jnb     loc_140009F1A
0x140009e8e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009e95  jz      short loc_140009EB7
0x140009e97  mov     rcx, cs:WPP_GLOBAL_Control
0x140009e9e  lea     r9d, [r13+2Ch]
0x140009ea2  mov     [rsp+88h+var_60], ebx
0x140009ea6  mov     r8d, r13d
0x140009ea9  mov     [rsp+88h+var_68], rdi
0x140009eae  mov     rcx, [rcx+40h]
0x140009eb2  call    WPP_RECORDER_SF_d
0x140009eb7  mov     r15d, 0C0000043h
0x140009ebd  jmp     loc_140009F95
0x140009ec2  mov     ebx, r14d
0x140009ec5  mov     eax, ebx
0x140009ec7  add     rax, rax
0x140009eca  cmp     byte ptr [rbp+rax*8+88h], 0
0x140009ed2  jnz     short loc_140009EDC
0x140009ed4  mov     eax, [rbp+5Ch]
0x140009ed7  bt      eax, ebx
0x140009eda  jnb     short loc_140009EEF
0x140009edc  add     ebx, r14d
0x140009edf  cmp     ebx, 1Eh
0x140009ee2  jbe     short loc_140009EC5
0x140009ee4  mov     r15d, 0C0000209h
0x140009eea  jmp     loc_140009F95
0x140009eef  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009ef6  jz      short loc_140009F1A
0x140009ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x140009eff  mov     r9d, 3Ah ; ':'
0x140009f05  mov     [rsp+88h+var_60], ebx
0x140009f09  mov     r8d, r13d
0x140009f0c  mov     [rsp+88h+var_68], rdi
0x140009f11  mov     rcx, [rcx+40h]
0x140009f15  call    WPP_RECORDER_SF_d
0x140009f1a  lea     rcx, [rbp+18h]
0x140009f1e  mov     edx, 52444441h
0x140009f23  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009f2a  mov     r8d, 5D5h
0x140009f30  call    RefObj_AddRefEx
0x140009f35  lea     rcx, [r12+18h]
0x140009f3a  mov     [r12+40h], rbp
0x140009f3f  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009f46  mov     edx, 20494454h
0x140009f4b  mov     r8d, 5D7h
0x140009f51  call    RefObj_AddRefEx
0x140009f56  lea     rax, [rbp+70h]
0x140009f5a  mov     rcx, [rax+8]
0x140009f5e  cmp     [rcx], rax
0x140009f61  jz      short loc_140009F6A
0x140009f63  mov     ecx, 3
0x140009f68  int     29h; Win8: RtlFailFast(ecx)
0x140009f6a  mov     [r12], rax
0x140009f6e  mov     [r12+8], rcx
0x140009f73  mov     [rcx], r12
0x140009f76  mov     ecx, ebx
0x140009f78  mov     [rax+8], r12
0x140009f7c  mov     rax, [rsp+88h+arg_8]
0x140009f84  mov     [r12+70h], ebx
0x140009f89  shl     r14d, cl
0x140009f8c  or      [rbp+5Ch], r14d
0x140009f90  mov     [r12+48h], rax
0x140009f95  mov     dl, [rbp+38h]; NewIrql
0x140009f98  lea     rcx, [rbp+30h]; SpinLock
0x140009f9c  call    cs:__imp_KeReleaseSpinLock
0x140009fa3  nop     dword ptr [rax+rax+00h]
0x140009fa8  test    r15d, r15d
0x140009fab  jns     short loc_140009FC9
0x140009fad  lea     rcx, [r12+18h]
0x140009fb2  mov     edx, 54494E49h
0x140009fb7  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009fbe  mov     r8d, 5E7h
0x140009fc4  call    RefObj_ReleaseEx
0x140009fc9  mov     rax, [rsp+88h+arg_10]
0x140009fd1  mov     [rax], r12
0x140009fd4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009fdb  jz      short loc_14000A000
0x140009fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140009fe4  mov     r9d, 3Ch ; '<'
0x140009fea  mov     [rsp+88h+var_60], r15d
0x140009fef  mov     r8d, r13d
0x140009ff2  mov     [rsp+88h+var_68], rdi
0x140009ff7  mov     rcx, [rcx+40h]
0x140009ffb  call    WPP_RECORDER_SF_d
0x14000a000  mov     eax, r15d
0x14000a003  jmp     short loc_14000A03F
0x14000a005  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000a00c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000a013  jz      short loc_14000A03A
0x14000a015  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a01c  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000a023  mov     r9d, 36h ; '6'
0x14000a029  mov     [rsp+88h+var_68], rdi
0x14000a02e  mov     r8d, r14d
0x14000a031  mov     rcx, [rcx+40h]
0x14000a035  call    WPP_RECORDER_SF_
0x14000a03a  mov     eax, 0C0000207h
0x14000a03f  mov     rbx, [rsp+88h+arg_0]
0x14000a047  add     rsp, 50h
0x14000a04b  pop     r15
0x14000a04d  pop     r14
0x14000a04f  pop     r13
0x14000a051  pop     r12
0x14000a053  pop     rdi
0x14000a054  pop     rsi
0x14000a055  pop     rbp
0x14000a056  retn
```
