# Dfdll::CSubscription::EnsureInitialization(void)

- ea: `0x18000a040`
- end: `0x18000a219`
- name: `?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ`
- size: `473`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `17`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000949c`
- `0x18000972c`
- `0x180009c44`
- `0x180009e0c`
- `0x18000a2ac`
- `0x18000aa14`
- `0x18000ab8c`
- `0x18000c800`
- `0x18000c8e8`
- `0x18000ca34`
- `0x18000cac8`
- `0x18000d9b8`
- `0x18000dadc`
- `0x180010bf4`
- `0x180010d18`
- `0x180010ea8`
- `0x180010f34`

## callees

- `0x18000a040`
- `0x18000d59c`
- `0x18001efd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dfdll::CSubscription::EnsureInitialization(Dfdll::CSubscription *this)
{
  int v2; // ebx
  char v3; // di

  v2 = Dfdll::CSubscription::InitializeIsolation(this);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(void *, __int64))(Dfdll::CSubscription::_criticalSection + 40LL))(
           &Dfdll::CSubscription::_criticalSection,
           0xFFFFFFFFLL);
    if ( v2 >= 0 )
    {
      v3 = 1;
      if ( (*((_QWORD *)this + 16)
         || (v2 = ((__int64 (__fastcall *)(_QWORD, _QWORD, GUID *))Dfdll::CSubscription::_pfnGetUserStore)(
                    0,
                    0,
                    &GUID_a5c62f6d_5e3e_4cd9_b345_6b281d7a1d1e),
             v2 >= 0))
        && (*((_QWORD *)this + 18)
         || (v2 = ((__int64 (*)(void))Dfdll::CSubscription::_pfnGetIdentityAuthority)(), v2 >= 0))
        && (*((_QWORD *)this + 20) || (v2 = ((__int64 (*)(void))Dfdll::CSubscription::_pfnGetAppIdAuthority)(), v2 >= 0)) )
      {
        v2 = (*(__int64 (__fastcall **)(void *))(Dfdll::CSubscription::_criticalSection + 48LL))(&Dfdll::CSubscription::_criticalSection);
        if ( v2 >= 0 )
        {
          v3 = 0;
          v2 = 0;
        }
        if ( v2 >= 0 )
        {
          if ( v3 )
            (*(void (__fastcall **)(void *))(Dfdll::CSubscription::_criticalSection + 48LL))(&Dfdll::CSubscription::_criticalSection);
          return 0;
        }
        else if ( v3 )
        {
          (*(void (__fastcall **)(void *))(Dfdll::CSubscription::_criticalSection + 48LL))(&Dfdll::CSubscription::_criticalSection);
        }
      }
      else
      {
        (*(void (__fastcall **)(void *))(Dfdll::CSubscription::_criticalSection + 48LL))(&Dfdll::CSubscription::_criticalSection);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000a040  mov     [rsp+arg_0], rbx
0x18000a045  mov     [rsp+arg_8], rsi
0x18000a04a  mov     [rsp+arg_10], rdi
0x18000a04f  push    r14
0x18000a051  sub     rsp, 50h
0x18000a055  mov     rsi, rcx
0x18000a058  call    ?InitializeIsolation@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::InitializeIsolation(void)
0x18000a05d  mov     ebx, eax
0x18000a05f  test    eax, eax
0x18000a061  js      loc_18000A201
0x18000a067  lea     rax, ??_7CLock@Dfdll@@6B@; const Dfdll::CLock::`vftable'
0x18000a06e  mov     [rsp+58h+var_28], rax
0x18000a073  lea     r14, ?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a07a  mov     [rsp+58h+var_20], r14
0x18000a07f  xor     dil, dil
0x18000a082  mov     [rsp+58h+var_18], dil
0x18000a087  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a08e  or      edx, 0FFFFFFFFh
0x18000a091  mov     rcx, r14
0x18000a094  mov     rax, [rax+28h]
0x18000a098  call    cs:__guard_dispatch_icall_fptr
0x18000a09e  mov     ebx, eax
0x18000a0a0  xor     al, al
0x18000a0a2  test    ebx, ebx
0x18000a0a4  js      short loc_18000A0B7
0x18000a0a6  mov     dil, 1
0x18000a0a9  mov     [rsp+58h+var_18], dil
0x18000a0ae  xor     ebx, ebx
0x18000a0b0  mov     al, dil
0x18000a0b3  test    ebx, ebx
0x18000a0b5  jns     short loc_18000A0D5
0x18000a0b7  test    al, al
0x18000a0b9  jz      short loc_18000A0D0
0x18000a0bb  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a0c2  mov     rcx, r14
0x18000a0c5  mov     rax, [rax+30h]
0x18000a0c9  call    cs:__guard_dispatch_icall_fptr
0x18000a0cf  nop
0x18000a0d0  jmp     loc_18000A201
0x18000a0d5  lea     r9, [rsi+80h]
0x18000a0dc  cmp     qword ptr [r9], 0
0x18000a0e0  jnz     short loc_18000A11F
0x18000a0e2  lea     r8, _GUID_a5c62f6d_5e3e_4cd9_b345_6b281d7a1d1e
0x18000a0e9  xor     edx, edx
0x18000a0eb  xor     ecx, ecx
0x18000a0ed  mov     rax, cs:?_pfnGetUserStore@CSubscription@Dfdll@@1P6AJKPEAXAEBU_GUID@@PEAPEAUIStore@@@ZEA; long (*Dfdll::CSubscription::_pfnGetUserStore)(ulong,void *,_GUID const &,IStore * *)
0x18000a0f4  call    cs:__guard_dispatch_icall_fptr
0x18000a0fa  mov     ebx, eax
0x18000a0fc  test    eax, eax
0x18000a0fe  jns     short loc_18000A11F
0x18000a100  test    dil, dil
0x18000a103  jz      short loc_18000A11A
0x18000a105  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a10c  mov     rcx, r14
0x18000a10f  mov     rax, [rax+30h]
0x18000a113  call    cs:__guard_dispatch_icall_fptr
0x18000a119  nop
0x18000a11a  jmp     loc_18000A201
0x18000a11f  lea     rcx, [rsi+90h]
0x18000a126  cmp     qword ptr [rcx], 0
0x18000a12a  jnz     short loc_18000A15E
0x18000a12c  mov     rax, cs:?_pfnGetIdentityAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIIdentityAuthority@@@ZEA; long (*Dfdll::CSubscription::_pfnGetIdentityAuthority)(IIdentityAuthority * *)
0x18000a133  call    cs:__guard_dispatch_icall_fptr
0x18000a139  mov     ebx, eax
0x18000a13b  test    eax, eax
0x18000a13d  jns     short loc_18000A15E
0x18000a13f  test    dil, dil
0x18000a142  jz      short loc_18000A159
0x18000a144  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a14b  mov     rcx, r14
0x18000a14e  mov     rax, [rax+30h]
0x18000a152  call    cs:__guard_dispatch_icall_fptr
0x18000a158  nop
0x18000a159  jmp     loc_18000A201
0x18000a15e  lea     rcx, [rsi+0A0h]
0x18000a165  cmp     qword ptr [rcx], 0
0x18000a169  jnz     short loc_18000A19A
0x18000a16b  mov     rax, cs:?_pfnGetAppIdAuthority@CSubscription@Dfdll@@1P6AJPEAPEAUIAppIdAuthority@@@ZEA; long (*Dfdll::CSubscription::_pfnGetAppIdAuthority)(IAppIdAuthority * *)
0x18000a172  call    cs:__guard_dispatch_icall_fptr
0x18000a178  mov     ebx, eax
0x18000a17a  test    eax, eax
0x18000a17c  jns     short loc_18000A19A
0x18000a17e  test    dil, dil
0x18000a181  jz      short loc_18000A198
0x18000a183  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a18a  mov     rcx, r14
0x18000a18d  mov     rax, [rax+30h]
0x18000a191  call    cs:__guard_dispatch_icall_fptr
0x18000a197  nop
0x18000a198  jmp     short loc_18000A201
0x18000a19a  test    dil, dil
0x18000a19d  jnz     short loc_18000A1A6
0x18000a19f  mov     ebx, 800710D8h
0x18000a1a4  jmp     short loc_18000A1C9
0x18000a1a6  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a1ad  mov     rcx, r14
0x18000a1b0  mov     rax, [rax+30h]
0x18000a1b4  call    cs:__guard_dispatch_icall_fptr
0x18000a1ba  mov     ebx, eax
0x18000a1bc  test    eax, eax
0x18000a1be  js      short loc_18000A1C5
0x18000a1c0  xor     dil, dil
0x18000a1c3  xor     ebx, ebx
0x18000a1c5  test    ebx, ebx
0x18000a1c7  jns     short loc_18000A1E5
0x18000a1c9  test    dil, dil
0x18000a1cc  jz      short loc_18000A1E3
0x18000a1ce  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a1d5  mov     rcx, r14
0x18000a1d8  mov     rax, [rax+30h]
0x18000a1dc  call    cs:__guard_dispatch_icall_fptr
0x18000a1e2  nop
0x18000a1e3  jmp     short loc_18000A201
0x18000a1e5  test    dil, dil
0x18000a1e8  jz      short loc_18000A1FF
0x18000a1ea  mov     rax, cs:?_criticalSection@CSubscription@Dfdll@@1VCCriticialSection@2@A; Dfdll::CCriticialSection Dfdll::CSubscription::_criticalSection
0x18000a1f1  mov     rcx, r14
0x18000a1f4  mov     rax, [rax+30h]
0x18000a1f8  call    cs:__guard_dispatch_icall_fptr
0x18000a1fe  nop
0x18000a1ff  xor     ebx, ebx
0x18000a201  mov     eax, ebx
0x18000a203  mov     rbx, [rsp+58h+arg_0]
0x18000a208  mov     rsi, [rsp+58h+arg_8]
0x18000a20d  mov     rdi, [rsp+58h+arg_10]
0x18000a212  add     rsp, 50h
0x18000a216  pop     r14
0x18000a218  retn
```
