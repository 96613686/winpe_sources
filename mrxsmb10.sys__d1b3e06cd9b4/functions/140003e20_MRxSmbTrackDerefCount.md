# MRxSmbTrackDerefCount

- ea: `0x140003e20`
- end: `0x140004028`
- name: `MRxSmbTrackDerefCount`
- size: `520`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x140002050`
- `0x140002614`
- `0x140003450`
- `0x14000cc00`
- `0x14000ce24`
- `0x14000d314`
- `0x140011590`
- `0x140013660`
- `0x140013700`
- `0x140014a70`
- `0x140028310`
- `0x1400357b0`
- `0x1400358dc`
- `0x140038f6c`
- `0x1400394f0`
- `0x14003e06c`
- `0x14003e364`
- `0x14003e560`
- `0x14003e934`
- `0x140042d00`
- `0x140042e64`
- `0x140042ee0`
- `0x14004eb70`
- `0x140053db0`

## callees

- `0x140003e20`
- `0x140012364`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x140004017`
- `ntoskrnl!DbgPrint` at `0x140004017`

## pseudocode

```c
void __fastcall MRxSmbTrackDerefCount(unsigned __int8 *a1, __int64 a2, int a3)
{
  unsigned int v3; // ebp
  unsigned int v5; // r14d
  int v7; // ecx
  int v9; // ecx
  const CHAR *v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-48h]

  v3 = *((_DWORD *)a1 + 3);
  v5 = *((_DWORD *)a1 + 2);
  v7 = *a1;
  if ( v7 != 4 )
  {
    if ( v7 )
    {
      v9 = v7 - 1;
      if ( v9 )
      {
        if ( v9 != 1 || (MRxSmbReferenceTracingValue & 4) == 0 )
          return;
        if ( MRxSmbReferenceTracingValue < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_qddls(WPP_GLOBAL_Control->AttachedDevice, 55, a3, (_DWORD)a1, v3, v5, a3, a2);
        }
        if ( (MRxSmbReferenceTracingValue & 0x40000000) == 0 )
          return;
        v10 = "Deref SessionEntry %p %d %d %ld %s\n";
      }
      else
      {
        if ( (MRxSmbReferenceTracingValue & 2) == 0 )
          return;
        if ( MRxSmbReferenceTracingValue < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_qddls(WPP_GLOBAL_Control->AttachedDevice, 54, a3, (_DWORD)a1, v3, v5, a3, a2);
        }
        if ( (MRxSmbReferenceTracingValue & 0x40000000) == 0 )
          return;
        v10 = "Deref NetRootEntry %p %d %d %ld %s\n";
      }
    }
    else
    {
      if ( (MRxSmbReferenceTracingValue & 1) == 0 )
        return;
      if ( MRxSmbReferenceTracingValue < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_qddls(WPP_GLOBAL_Control->AttachedDevice, 53, a3, (_DWORD)a1, v3, v5, a3, a2);
      }
      if ( (MRxSmbReferenceTracingValue & 0x40000000) == 0 )
        return;
      v10 = "Deref ServerEntry %p %d %d %ld %s\n";
    }
LABEL_34:
    LODWORD(v11) = a3;
    DbgPrint(v10, a1, v3, v5, v11, a2);
    return;
  }
  if ( (MRxSmbReferenceTracingValue & 8) != 0 )
  {
    if ( MRxSmbReferenceTracingValue < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qddls(WPP_GLOBAL_Control->AttachedDevice, 56, a3, (_DWORD)a1, v3, v5, a3, a2);
    }
    if ( (MRxSmbReferenceTracingValue & 0x40000000) != 0 )
    {
      v10 = "Deref VNetRootContext %p %d %d %ld %s\n";
      goto LABEL_34;
    }
  }
}

```

## disassembly

```asm
0x140003e20  push    rbx
0x140003e22  push    rbp
0x140003e23  push    rsi
0x140003e24  push    rdi
0x140003e25  push    r14
0x140003e27  sub     rsp, 40h
0x140003e2b  mov     ebp, [rcx+0Ch]
0x140003e2e  mov     rbx, rcx
0x140003e31  mov     r14d, [rcx+8]
0x140003e35  mov     edi, r8d
0x140003e38  movzx   ecx, byte ptr [rcx]
0x140003e3b  mov     rsi, rdx
0x140003e3e  cmp     ecx, 4
0x140003e41  jnz     short loc_140003E5D
0x140003e43  mov     eax, cs:MRxSmbReferenceTracingValue
0x140003e49  test    al, 8
0x140003e4b  jnz     loc_140003FAB
0x140003e51  add     rsp, 40h
0x140003e55  pop     r14
0x140003e57  pop     rdi
0x140003e58  pop     rsi
0x140003e59  pop     rbp
0x140003e5a  pop     rbx
0x140003e5b  retn
0x140003e5d  test    ecx, ecx
0x140003e5f  jz      loc_140003F41
0x140003e65  sub     ecx, 1
0x140003e68  jz      short loc_140003ED4
0x140003e6a  cmp     ecx, 1
0x140003e6d  jnz     short loc_140003E51
0x140003e6f  mov     eax, cs:MRxSmbReferenceTracingValue
0x140003e75  test    al, 4
0x140003e77  jz      short loc_140003E51
0x140003e79  test    eax, eax
0x140003e7b  jns     short loc_140003EBC
0x140003e7d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140003e84  lea     rax, WPP_GLOBAL_Control
0x140003e8b  cmp     rcx, rax
0x140003e8e  jz      short loc_140003EBC
0x140003e90  test    dword ptr [rcx+2Ch], 200h
0x140003e97  jz      short loc_140003EBC
0x140003e99  mov     rcx, [rcx+18h]
0x140003e9d  mov     edx, 37h ; '7'
0x140003ea2  mov     [rsp+68h+var_30], rsi
0x140003ea7  mov     r9, rbx
0x140003eaa  mov     [rsp+68h+var_38], edi
0x140003eae  mov     dword ptr [rsp+68h+var_40], r14d
0x140003eb3  mov     dword ptr [rsp+68h+var_48], ebp
0x140003eb7  call    WPP_SF_qddls
0x140003ebc  test    cs:MRxSmbReferenceTracingValue, 40000000h
0x140003ec6  jz      short loc_140003E51
0x140003ec8  lea     rcx, aDerefSessionen; "Deref SessionEntry %p %d %d %ld %s\n"
0x140003ecf  jmp     loc_140004005
0x140003ed4  mov     eax, cs:MRxSmbReferenceTracingValue
0x140003eda  test    al, 2
0x140003edc  jz      loc_140003E51
0x140003ee2  test    eax, eax
0x140003ee4  jns     short loc_140003F25
0x140003ee6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140003eed  lea     rax, WPP_GLOBAL_Control
0x140003ef4  cmp     rcx, rax
0x140003ef7  jz      short loc_140003F25
0x140003ef9  test    dword ptr [rcx+2Ch], 200h
0x140003f00  jz      short loc_140003F25
0x140003f02  mov     rcx, [rcx+18h]
0x140003f06  mov     edx, 36h ; '6'
0x140003f0b  mov     [rsp+68h+var_30], rsi
0x140003f10  mov     r9, rbx
0x140003f13  mov     [rsp+68h+var_38], edi
0x140003f17  mov     dword ptr [rsp+68h+var_40], r14d
0x140003f1c  mov     dword ptr [rsp+68h+var_48], ebp
0x140003f20  call    WPP_SF_qddls
0x140003f25  test    cs:MRxSmbReferenceTracingValue, 40000000h
0x140003f2f  jz      loc_140003E51
0x140003f35  lea     rcx, aDerefNetrooten; "Deref NetRootEntry %p %d %d %ld %s\n"
0x140003f3c  jmp     loc_140004005
0x140003f41  mov     eax, cs:MRxSmbReferenceTracingValue
0x140003f47  test    al, 1
0x140003f49  jz      loc_140003E51
0x140003f4f  test    eax, eax
0x140003f51  jns     short loc_140003F92
0x140003f53  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140003f5a  lea     rax, WPP_GLOBAL_Control
0x140003f61  cmp     rcx, rax
0x140003f64  jz      short loc_140003F92
0x140003f66  test    dword ptr [rcx+2Ch], 200h
0x140003f6d  jz      short loc_140003F92
0x140003f6f  mov     rcx, [rcx+18h]
0x140003f73  mov     edx, 35h ; '5'
0x140003f78  mov     [rsp+68h+var_30], rsi
0x140003f7d  mov     r9, rbx
0x140003f80  mov     [rsp+68h+var_38], edi
0x140003f84  mov     dword ptr [rsp+68h+var_40], r14d
0x140003f89  mov     dword ptr [rsp+68h+var_48], ebp
0x140003f8d  call    WPP_SF_qddls
0x140003f92  test    cs:MRxSmbReferenceTracingValue, 40000000h
0x140003f9c  jz      loc_140003E51
0x140003fa2  lea     rcx, aDerefServerent; "Deref ServerEntry %p %d %d %ld %s\n"
0x140003fa9  jmp     short loc_140004005
0x140003fab  test    eax, eax
0x140003fad  jns     short loc_140003FEE
0x140003faf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140003fb6  lea     rax, WPP_GLOBAL_Control
0x140003fbd  cmp     rcx, rax
0x140003fc0  jz      short loc_140003FEE
0x140003fc2  test    dword ptr [rcx+2Ch], 200h
0x140003fc9  jz      short loc_140003FEE
0x140003fcb  mov     rcx, [rcx+18h]
0x140003fcf  mov     edx, 38h ; '8'
0x140003fd4  mov     [rsp+68h+var_30], rsi
0x140003fd9  mov     r9, rbx
0x140003fdc  mov     [rsp+68h+var_38], edi
0x140003fe0  mov     dword ptr [rsp+68h+var_40], r14d
0x140003fe5  mov     dword ptr [rsp+68h+var_48], ebp
0x140003fe9  call    WPP_SF_qddls
0x140003fee  test    cs:MRxSmbReferenceTracingValue, 40000000h
0x140003ff8  jz      loc_140003E51
0x140003ffe  lea     rcx, aDerefVnetrootc; "Deref VNetRootContext %p %d %d %ld %s\n"
0x140004005  mov     [rsp+68h+var_40], rsi
0x14000400a  mov     r9d, r14d
0x14000400d  mov     r8d, ebp
0x140004010  mov     dword ptr [rsp+68h+var_48], edi
0x140004014  mov     rdx, rbx
0x140004017  call    cs:__imp_DbgPrint
0x14000401e  nop     dword ptr [rax+rax+00h]
0x140004023  jmp     loc_140003E51
```
