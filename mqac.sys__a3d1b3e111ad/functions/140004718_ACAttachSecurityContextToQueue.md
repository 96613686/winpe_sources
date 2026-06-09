# ACAttachSecurityContextToQueue

- ea: `0x140004718`
- end: `0x1400047f4`
- name: `ACAttachSecurityContextToQueue`
- size: `220`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140001c04`
- `0x140004718`
- `0x14000e9a8`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140004739`
- `ntoskrnl!ProbeForRead` at `0x140004739`

## pseudocode

```c
__int64 __fastcall ACAttachSecurityContextToQueue(__int64 a1, volatile void *a2)
{
  struct DriverSecurityContext *v4; // rax

  ProbeForRead(a2, 0x40u, 1u);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 20LL) & 0x10) != 0 )
    return 0;
  v4 = DriverSecurityContext::NewCopy((const struct CACSecurityContext *)a2);
  if ( v4 )
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 32) + 8LL) = v4;
    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 20LL) |= 0x10u;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 221, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140004718  mov     [rsp+arg_0], rbx
0x14000471d  mov     [rsp+arg_8], rdx
0x140004722  push    rdi
0x140004723  sub     rsp, 30h
0x140004727  mov     rbx, rdx
0x14000472a  mov     rdi, rcx
0x14000472d  mov     edx, 40h ; '@'; Length
0x140004732  lea     r8d, [rdx-3Fh]; Alignment
0x140004736  mov     rcx, rbx; Address
0x140004739  call    cs:__imp_ProbeForRead
0x140004740  nop     dword ptr [rax+rax+00h]
0x140004745  mov     rax, [rdi+20h]
0x140004749  mov     ecx, [rax+14h]
0x14000474c  test    cl, 10h
0x14000474f  jnz     short loc_1400047A7
0x140004751  mov     rcx, rbx; struct CACSecurityContext *
0x140004754  call    ?NewCopy@DriverSecurityContext@@SAPEAV1@PEBVCACSecurityContext@@@Z; DriverSecurityContext::NewCopy(CACSecurityContext const *)
0x140004759  mov     rcx, rax
0x14000475c  test    rax, rax
0x14000475f  jnz     short loc_140004797
0x140004761  lea     rax, WPP_GLOBAL_Control
0x140004768  mov     rcx, cs:WPP_GLOBAL_Control
0x14000476f  cmp     rcx, rax
0x140004772  jz      short loc_140004790
0x140004774  mov     eax, [rcx+6Ch]
0x140004777  test    al, 1
0x140004779  jz      short loc_140004790
0x14000477b  mov     edx, 0DDh
0x140004780  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004787  mov     rcx, [rcx+58h]
0x14000478b  call    WPP_SF_
0x140004790  mov     eax, 0C000009Ah
0x140004795  jmp     short loc_1400047E8
0x140004797  mov     rax, [rdi+20h]
0x14000479b  mov     [rax+8], rcx
0x14000479f  mov     rax, [rdi+20h]
0x1400047a3  or      dword ptr [rax+14h], 10h
0x1400047a7  xor     eax, eax
0x1400047a9  jmp     short loc_1400047E8
0x1400047ab  mov     ebx, eax
0x1400047ad  lea     rax, WPP_GLOBAL_Control
0x1400047b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047bb  cmp     rcx, rax
0x1400047be  jz      short loc_1400047E6
0x1400047c0  mov     edx, [rcx+6Ch]
0x1400047c3  test    dl, 1
0x1400047c6  jz      short loc_1400047E6
0x1400047c8  mov     edx, 0DEh
0x1400047cd  mov     [rsp+38h+var_18], ebx
0x1400047d1  mov     r9, [rsp+38h+arg_8]
0x1400047d6  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400047dd  mov     rcx, [rcx+58h]
0x1400047e1  call    WPP_SF_qD
0x1400047e6  mov     eax, ebx
0x1400047e8  mov     rbx, [rsp+38h+arg_0]
0x1400047ed  add     rsp, 30h
0x1400047f1  pop     rdi
0x1400047f2  retn
```
