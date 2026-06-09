# CServiceProvider::Initialize(IFunctionInstance *,_GUID const &,void * *)

- ea: `0x18000ad60`
- end: `0x18000aed5`
- name: `?Initialize@CServiceProvider@@UEAAJPEAUIFunctionInstance@@AEBU_GUID@@PEAPEAX@Z`
- size: `373`
- prototype: `__int64 __fastcall(CServiceProvider *__hidden this, struct IFunctionInstance *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000ad60`
- `0x18000b9b4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Initialize(
        CServiceProvider *this,
        struct IFunctionInstance *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v9; // rcx
  char *v10; // rdi
  unsigned int v11; // esi
  unsigned __int64 v12; // rcx

  if ( !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  if ( *(_QWORD *)&GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data1 == *(_QWORD *)&a3->Data1
    && *(_QWORD *)GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data4 == *(_QWORD *)a3->Data4
    || *(_QWORD *)&GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data1 == *(_QWORD *)&a3->Data1
    && *(_QWORD *)GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data4 == *(_QWORD *)a3->Data4
    || *(_QWORD *)&GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data1 == *(_QWORD *)&a3->Data1
    && *(_QWORD *)GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data4 == *(_QWORD *)a3->Data4 )
  {
    if ( !g_bInitialized )
      return 2147500037LL;
    if ( *((struct IFunctionInstance **)this + 8) != a2 )
    {
      ((void (__fastcall *)(struct IFunctionInstance *))a2->lpVtbl->AddRef)(a2);
      v9 = *((_QWORD *)this + 8);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 8) = a2;
    }
    v10 = (char *)this - 24;
    if ( *((_QWORD *)this + 8) )
    {
      v11 = CServiceProvider::Validate((CServiceProvider *)((char *)this - 24));
      if ( !v11 )
      {
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))((char *)this - 24);
        if ( *(_QWORD *)&GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data1 == *(_QWORD *)&a3->Data1
          && *(_QWORD *)GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data4 == *(_QWORD *)a3->Data4 )
        {
          v12 = (unsigned __int64)this - 16;
        }
        else
        {
          if ( *(_QWORD *)&GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data1 == *(_QWORD *)&a3->Data1
            && *(_QWORD *)GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data4 == *(_QWORD *)a3->Data4 )
          {
            *a4 = v10;
            return v11;
          }
          if ( *(_QWORD *)&GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data1 != *(_QWORD *)&a3->Data1
            || *(_QWORD *)GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data4 != *(_QWORD *)a3->Data4 )
          {
            return v11;
          }
          v12 = (unsigned __int64)this - 8;
        }
        *a4 = (void *)(v12 & -(__int64)(this != (CServiceProvider *)24));
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
    return v11;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000ad60  push    rbx
0x18000ad62  push    rbp
0x18000ad63  push    rsi
0x18000ad64  push    rdi
0x18000ad65  push    r14
0x18000ad67  sub     rsp, 20h
0x18000ad6b  mov     r14, r9
0x18000ad6e  mov     rbx, r8
0x18000ad71  mov     rdi, rdx
0x18000ad74  mov     rbp, rcx
0x18000ad77  test    rdx, rdx
0x18000ad7a  jnz     short loc_18000AD86
0x18000ad7c  mov     eax, 80070057h
0x18000ad81  jmp     loc_18000AECA
0x18000ad86  test    r14, r14
0x18000ad89  jnz     short loc_18000AD95
0x18000ad8b  mov     eax, 80004003h
0x18000ad90  jmp     loc_18000AECA
0x18000ad95  mov     rax, qword ptr cs:_GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data1
0x18000ad9c  cmp     rax, [r8]
0x18000ad9f  jnz     short loc_18000ADAE
0x18000ada1  mov     rax, qword ptr cs:_GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data4
0x18000ada8  cmp     rax, [r8+8]
0x18000adac  jz      short loc_18000ADE8
0x18000adae  mov     rax, qword ptr cs:_GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data1
0x18000adb5  cmp     rax, [r8]
0x18000adb8  jnz     short loc_18000ADC7
0x18000adba  mov     rax, qword ptr cs:_GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data4
0x18000adc1  cmp     rax, [r8+8]
0x18000adc5  jz      short loc_18000ADE8
0x18000adc7  mov     rax, qword ptr cs:_GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data1
0x18000adce  cmp     rax, [r8]
0x18000add1  jnz     loc_18000AEC5
0x18000add7  mov     rax, qword ptr cs:_GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data4
0x18000adde  cmp     rax, [r8+8]
0x18000ade2  jnz     loc_18000AEC5
0x18000ade8  cmp     cs:?g_bInitialized@@3HA, 0; int g_bInitialized
0x18000adef  jnz     short loc_18000ADFB
0x18000adf1  mov     eax, 80004005h
0x18000adf6  jmp     loc_18000AECA
0x18000adfb  cmp     [rcx+40h], rdi
0x18000adff  jz      short loc_18000AE29
0x18000ae01  mov     rax, [rdx]
0x18000ae04  mov     rcx, rdi
0x18000ae07  mov     rax, [rax+8]
0x18000ae0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae10  mov     rcx, [rbp+40h]
0x18000ae14  test    rcx, rcx
0x18000ae17  jz      short loc_18000AE25
0x18000ae19  mov     rax, [rcx]
0x18000ae1c  mov     rax, [rax+10h]
0x18000ae20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae25  mov     [rbp+40h], rdi
0x18000ae29  lea     rdi, [rbp-18h]
0x18000ae2d  cmp     qword ptr [rdi+58h], 0
0x18000ae32  jnz     short loc_18000AE3E
0x18000ae34  mov     esi, 80004005h
0x18000ae39  jmp     loc_18000AEC1
0x18000ae3e  mov     rcx, rdi; this
0x18000ae41  call    ?Validate@CServiceProvider@@IEAAJXZ; CServiceProvider::Validate(void)
0x18000ae46  mov     esi, eax
0x18000ae48  test    eax, eax
0x18000ae4a  jnz     short loc_18000AEC1
0x18000ae4c  mov     rcx, [rdi]
0x18000ae4f  mov     rax, [rcx+8]
0x18000ae53  mov     rcx, rdi
0x18000ae56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae5b  mov     rcx, qword ptr cs:_GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data1
0x18000ae62  cmp     rcx, [rbx]
0x18000ae65  jnz     short loc_18000AE7A
0x18000ae67  mov     rax, qword ptr cs:_GUID_0bd7e521_4da6_42d5_81ba_1981b6b94075.Data4
0x18000ae6e  cmp     rax, [rbx+8]
0x18000ae72  jnz     short loc_18000AE7A
0x18000ae74  lea     rcx, [rbp-10h]
0x18000ae78  jmp     short loc_18000AEB5
0x18000ae7a  mov     rax, qword ptr cs:_GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data1
0x18000ae81  cmp     rax, [rbx]
0x18000ae84  jnz     short loc_18000AE98
0x18000ae86  mov     rax, qword ptr cs:_GUID_eed366d0_35b8_4fc5_8d20_7e5bd31f6ded.Data4
0x18000ae8d  cmp     rax, [rbx+8]
0x18000ae91  jnz     short loc_18000AE98
0x18000ae93  mov     [r14], rdi
0x18000ae96  jmp     short loc_18000AEC1
0x18000ae98  mov     rax, qword ptr cs:_GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data1
0x18000ae9f  cmp     rax, [rbx]
0x18000aea2  jnz     short loc_18000AEC1
0x18000aea4  mov     rax, qword ptr cs:_GUID_58cfdfec_9ef3_496e_a174_4fa9f56eda77.Data4
0x18000aeab  cmp     rax, [rbx+8]
0x18000aeaf  jnz     short loc_18000AEC1
0x18000aeb1  lea     rcx, [rbp-8]
0x18000aeb5  neg     rdi
0x18000aeb8  sbb     rax, rax
0x18000aebb  and     rax, rcx
0x18000aebe  mov     [r14], rax
0x18000aec1  mov     eax, esi
0x18000aec3  jmp     short loc_18000AECA
0x18000aec5  mov     eax, 80004002h
0x18000aeca  add     rsp, 20h
0x18000aece  pop     r14
0x18000aed0  pop     rdi
0x18000aed1  pop     rsi
0x18000aed2  pop     rbp
0x18000aed3  pop     rbx
0x18000aed4  retn
```
