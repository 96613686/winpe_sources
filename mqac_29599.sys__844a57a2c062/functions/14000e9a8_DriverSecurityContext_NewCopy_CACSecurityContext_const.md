# DriverSecurityContext::NewCopy(CACSecurityContext const *)

- ea: `0x14000e9a8`
- end: `0x14000eb5a`
- name: `?NewCopy@DriverSecurityContext@@SAPEAV1@PEBVCACSecurityContext@@@Z`
- size: `434`
- prototype: `struct DriverSecurityContext *__fastcall(const struct CACSecurityContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004718`

## callees

- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x140003af0`
- `0x14000e414`
- `0x14000e488`
- `0x14000e5f4`
- `0x14000e710`
- `0x14000e9a8`

## pseudocode

```c
struct DriverSecurityContext *__fastcall DriverSecurityContext::NewCopy(const struct CACSecurityContext *a1)
{
  DriverSecurityContext *v2; // rax
  DriverSecurityContext *v3; // rbx
  unsigned int v5; // edx
  unsigned int v6; // edx
  unsigned int v7; // edx

  v2 = (DriverSecurityContext *)operator new(0x40u, 0x100u, 0x4451514Du, LowPoolPriority);
  if ( v2 )
    v3 = DriverSecurityContext::DriverSecurityContext(v2, a1);
  else
    v3 = 0;
  if ( v3 )
  {
    if ( DriverSecurityContext::AllocateAndCopySid(v3, (volatile void **)a1) )
    {
      if ( DriverSecurityContext::AllocateAndCopyUserCert(v3, *((void **)a1 + 1), *((_DWORD *)a1 + 10)) )
      {
        if ( DriverSecurityContext::AllocateAndCopyProviderName(v3, *((const wchar_t **)a1 + 2), *((_DWORD *)a1 + 11)) )
        {
          return v3;
        }
        else
        {
          DriverSecurityContext::`scalar deleting destructor'(v3, v7);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 13, &WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
          }
          return 0;
        }
      }
      else
      {
        DriverSecurityContext::`scalar deleting destructor'(v3, v6);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 12, &WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
        }
        return 0;
      }
    }
    else
    {
      DriverSecurityContext::`scalar deleting destructor'(v3, v5);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 11, &WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
      }
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 10, &WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14000e9a8  mov     [rsp+arg_0], rbx
0x14000e9ad  push    rdi
0x14000e9ae  sub     rsp, 20h
0x14000e9b2  mov     rdi, rcx
0x14000e9b5  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000e9b8  mov     edx, 100h; unsigned __int64
0x14000e9bd  mov     r8d, 4451514Dh; unsigned int
0x14000e9c3  lea     ecx, [r9+40h]; unsigned __int64
0x14000e9c7  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000e9cc  test    rax, rax
0x14000e9cf  jz      short loc_14000E9E1
0x14000e9d1  mov     rdx, rdi; struct CACSecurityContext *
0x14000e9d4  mov     rcx, rax; this
0x14000e9d7  call    ??0DriverSecurityContext@@AEAA@PEBVCACSecurityContext@@@Z; DriverSecurityContext::DriverSecurityContext(CACSecurityContext const *)
0x14000e9dc  mov     rbx, rax
0x14000e9df  jmp     short loc_14000E9E3
0x14000e9e1  xor     ebx, ebx
0x14000e9e3  mov     [rsp+28h+arg_8], rbx
0x14000e9e8  test    rbx, rbx
0x14000e9eb  jnz     short loc_14000EA21
0x14000e9ed  lea     rax, WPP_GLOBAL_Control
0x14000e9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9fb  cmp     rcx, rax
0x14000e9fe  jz      short loc_14000EA1A
0x14000ea00  mov     eax, [rcx+6Ch]
0x14000ea03  test    al, 1
0x14000ea05  jz      short loc_14000EA1A
0x14000ea07  lea     edx, [rbx+0Ah]
0x14000ea0a  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000ea11  mov     rcx, [rcx+58h]
0x14000ea15  call    WPP_SF_
0x14000ea1a  xor     eax, eax
0x14000ea1c  jmp     loc_14000EB4E
0x14000ea21  mov     rdx, rdi; struct CACSecurityContext *
0x14000ea24  mov     rcx, rbx; this
0x14000ea27  call    ?AllocateAndCopySid@DriverSecurityContext@@AEAA_NPEBVCACSecurityContext@@@Z; DriverSecurityContext::AllocateAndCopySid(CACSecurityContext const *)
0x14000ea2c  mov     rcx, rbx; this
0x14000ea2f  test    al, al
0x14000ea31  jnz     short loc_14000EA6E
0x14000ea33  call    ??_GDriverSecurityContext@@QEAAPEAXI@Z; DriverSecurityContext::`scalar deleting destructor'(uint)
0x14000ea38  lea     rax, WPP_GLOBAL_Control
0x14000ea3f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea46  cmp     rcx, rax
0x14000ea49  jz      short loc_14000EA67
0x14000ea4b  mov     eax, [rcx+6Ch]
0x14000ea4e  test    al, 1
0x14000ea50  jz      short loc_14000EA67
0x14000ea52  mov     edx, 0Bh
0x14000ea57  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000ea5e  mov     rcx, [rcx+58h]
0x14000ea62  call    WPP_SF_
0x14000ea67  xor     eax, eax
0x14000ea69  jmp     loc_14000EB4E
0x14000ea6e  mov     r8d, [rdi+28h]; unsigned int
0x14000ea72  mov     rdx, [rdi+8]; void *
0x14000ea76  call    ?AllocateAndCopyUserCert@DriverSecurityContext@@AEAA_NPEAXK@Z; DriverSecurityContext::AllocateAndCopyUserCert(void *,ulong)
0x14000ea7b  mov     rcx, rbx; this
0x14000ea7e  test    al, al
0x14000ea80  jnz     short loc_14000EABD
0x14000ea82  call    ??_GDriverSecurityContext@@QEAAPEAXI@Z; DriverSecurityContext::`scalar deleting destructor'(uint)
0x14000ea87  lea     rax, WPP_GLOBAL_Control
0x14000ea8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea95  cmp     rcx, rax
0x14000ea98  jz      short loc_14000EAB6
0x14000ea9a  mov     eax, [rcx+6Ch]
0x14000ea9d  test    al, 1
0x14000ea9f  jz      short loc_14000EAB6
0x14000eaa1  mov     edx, 0Ch
0x14000eaa6  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000eaad  mov     rcx, [rcx+58h]
0x14000eab1  call    WPP_SF_
0x14000eab6  xor     eax, eax
0x14000eab8  jmp     loc_14000EB4E
0x14000eabd  mov     r8d, [rdi+2Ch]; unsigned int
0x14000eac1  mov     rdx, [rdi+10h]; wchar_t *
0x14000eac5  call    ?AllocateAndCopyProviderName@DriverSecurityContext@@AEAA_NPEB_WK@Z; DriverSecurityContext::AllocateAndCopyProviderName(wchar_t const *,ulong)
0x14000eaca  test    al, al
0x14000eacc  jnz     short loc_14000EB09
0x14000eace  mov     rcx, rbx; this
0x14000ead1  call    ??_GDriverSecurityContext@@QEAAPEAXI@Z; DriverSecurityContext::`scalar deleting destructor'(uint)
0x14000ead6  lea     rax, WPP_GLOBAL_Control
0x14000eadd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eae4  cmp     rcx, rax
0x14000eae7  jz      short loc_14000EB05
0x14000eae9  mov     eax, [rcx+6Ch]
0x14000eaec  test    al, 1
0x14000eaee  jz      short loc_14000EB05
0x14000eaf0  mov     edx, 0Dh
0x14000eaf5  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000eafc  mov     rcx, [rcx+58h]
0x14000eb00  call    WPP_SF_
0x14000eb05  xor     eax, eax
0x14000eb07  jmp     short loc_14000EB4E
0x14000eb09  jmp     short loc_14000EB4B
0x14000eb0b  mov     edi, eax
0x14000eb0d  mov     rcx, [rsp+28h+arg_8]; this
0x14000eb12  call    ??_GDriverSecurityContext@@QEAAPEAXI@Z; DriverSecurityContext::`scalar deleting destructor'(uint)
0x14000eb17  xor     ebx, ebx
0x14000eb19  lea     rax, WPP_GLOBAL_Control
0x14000eb20  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb27  cmp     rcx, rax
0x14000eb2a  jz      short loc_14000EB4B
0x14000eb2c  mov     edx, [rcx+6Ch]
0x14000eb2f  test    dl, 1
0x14000eb32  jz      short loc_14000EB4B
0x14000eb34  mov     r9d, edi
0x14000eb37  lea     edx, [rbx+0Eh]
0x14000eb3a  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000eb41  mov     rcx, [rcx+58h]
0x14000eb45  call    WPP_SF_d
0x14000eb4a  nop
0x14000eb4b  mov     rax, rbx
0x14000eb4e  mov     rbx, [rsp+28h+arg_0]
0x14000eb53  add     rsp, 20h
0x14000eb57  pop     rdi
0x14000eb58  retn
```
