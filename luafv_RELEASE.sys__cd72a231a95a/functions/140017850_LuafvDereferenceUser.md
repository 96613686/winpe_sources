# LuafvDereferenceUser

- ea: `0x140017850`
- end: `0x140017957`
- name: `LuafvDereferenceUser`
- size: `263`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140017850`
- `0x14001de78`
- `0x140024a3c`
- `0x140024bd0`

## callees

- `0x140001adc`
- `0x140017850`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14001788a`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14001788a`
- `ntoskrnl!ZwClose` at `0x1400178ae`
- `ntoskrnl!ZwClose` at `0x140017930`
- `ntoskrnl!ZwClose` at `0x1400178ae`
- `ntoskrnl!ZwClose` at `0x140017930`

## pseudocode

```c
__int64 __fastcall LuafvDereferenceUser(__int64 a1)
{
  __int64 result; // rax
  void *v3; // rcx
  HANDLE *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  *(_QWORD *)(a1 + 16) = MEMORY[0xFFFFF78000000014];
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    v3 = *(void **)(a1 + 56);
    if ( v3 )
      ObfDereferenceObjectWithTag(v3, 0x6661754Cu);
    v4 = (HANDLE *)(a1 + 184);
    if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
    {
      if ( *v4 )
      {
        ZwClose(*v4);
        *v4 = 0;
      }
      if ( *(_QWORD *)(a1 + 176) )
      {
        LuafvDereferenceUser();
        *(_QWORD *)(a1 + 176) = 0;
      }
    }
    v5 = *(_QWORD *)(a1 + 72);
    if ( v5 )
    {
      LuafvFreePool(v5);
      *(_OWORD *)(a1 + 64) = 0;
    }
    if ( (unsigned int)Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline() )
    {
      v6 = *(_QWORD *)(a1 + 128);
      if ( v6 )
      {
        LuafvFreePool(v6);
        *(_OWORD *)(a1 + 120) = 0;
      }
      v7 = *(_QWORD *)(a1 + 112);
      if ( v7 )
      {
        LuafvFreePool(v7);
        *(_OWORD *)(a1 + 104) = 0;
      }
      if ( *v4 )
      {
        ZwClose(*v4);
        *v4 = 0;
      }
    }
    return LuafvFreePool(a1);
  }
  return result;
}

```

## disassembly

```asm
0x140017850  mov     [rsp+arg_0], rbx
0x140017855  push    rdi
0x140017856  sub     rsp, 20h
0x14001785a  mov     rax, ds:0FFFFF78000000014h
0x140017864  mov     rbx, rcx
0x140017867  mov     [rcx+10h], rax
0x14001786b  or      eax, 0FFFFFFFFh
0x14001786e  lock xadd [rcx+18h], eax
0x140017873  cmp     eax, 1
0x140017876  jnz     loc_14001794B
0x14001787c  mov     rcx, [rcx+38h]; Object
0x140017880  test    rcx, rcx
0x140017883  jz      short loc_140017896
0x140017885  mov     edx, 6661754Ch; Tag
0x14001788a  call    cs:__imp_ObfDereferenceObjectWithTag
0x140017891  nop     dword ptr [rax+rax+00h]
0x140017896  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x14001789b  lea     rdi, [rbx+0B8h]
0x1400178a2  test    eax, eax
0x1400178a4  jz      short loc_1400178DD
0x1400178a6  mov     rcx, [rdi]; Handle
0x1400178a9  test    rcx, rcx
0x1400178ac  jz      short loc_1400178C1
0x1400178ae  call    cs:__imp_ZwClose
0x1400178b5  nop     dword ptr [rax+rax+00h]
0x1400178ba  mov     qword ptr [rdi], 0
0x1400178c1  mov     rcx, [rbx+0B0h]
0x1400178c8  test    rcx, rcx
0x1400178cb  jz      short loc_1400178DD
0x1400178cd  call    LuafvDereferenceUser
0x1400178d2  mov     qword ptr [rbx+0B0h], 0
0x1400178dd  mov     rcx, [rbx+48h]
0x1400178e1  test    rcx, rcx
0x1400178e4  jz      short loc_1400178F2
0x1400178e6  call    LuafvFreePool
0x1400178eb  xorps   xmm0, xmm0
0x1400178ee  movups  xmmword ptr [rbx+40h], xmm0
0x1400178f2  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x1400178f7  test    eax, eax
0x1400178f9  jz      short loc_140017943
0x1400178fb  mov     rcx, [rbx+80h]
0x140017902  test    rcx, rcx
0x140017905  jz      short loc_140017913
0x140017907  call    LuafvFreePool
0x14001790c  xorps   xmm0, xmm0
0x14001790f  movups  xmmword ptr [rbx+78h], xmm0
0x140017913  mov     rcx, [rbx+70h]
0x140017917  test    rcx, rcx
0x14001791a  jz      short loc_140017928
0x14001791c  call    LuafvFreePool
0x140017921  xorps   xmm0, xmm0
0x140017924  movups  xmmword ptr [rbx+68h], xmm0
0x140017928  mov     rcx, [rdi]; Handle
0x14001792b  test    rcx, rcx
0x14001792e  jz      short loc_140017943
0x140017930  call    cs:__imp_ZwClose
0x140017937  nop     dword ptr [rax+rax+00h]
0x14001793c  mov     qword ptr [rdi], 0
0x140017943  mov     rcx, rbx
0x140017946  call    LuafvFreePool
0x14001794b  mov     rbx, [rsp+28h+arg_0]
0x140017950  add     rsp, 20h
0x140017954  pop     rdi
0x140017955  retn
```
