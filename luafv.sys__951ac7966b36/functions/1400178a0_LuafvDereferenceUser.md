# LuafvDereferenceUser

- ea: `0x1400178a0`
- end: `0x1400179a7`
- name: `LuafvDereferenceUser`
- size: `263`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400178a0`
- `0x14001dec8`
- `0x140024a8c`
- `0x140024c20`

## callees

- `0x140001adc`
- `0x1400178a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400178da`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1400178da`
- `ntoskrnl!ZwClose` at `0x1400178fe`
- `ntoskrnl!ZwClose` at `0x140017980`
- `ntoskrnl!ZwClose` at `0x1400178fe`
- `ntoskrnl!ZwClose` at `0x140017980`

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
0x1400178a0  mov     [rsp+arg_0], rbx
0x1400178a5  push    rdi
0x1400178a6  sub     rsp, 20h
0x1400178aa  mov     rax, ds:0FFFFF78000000014h
0x1400178b4  mov     rbx, rcx
0x1400178b7  mov     [rcx+10h], rax
0x1400178bb  or      eax, 0FFFFFFFFh
0x1400178be  lock xadd [rcx+18h], eax
0x1400178c3  cmp     eax, 1
0x1400178c6  jnz     loc_14001799B
0x1400178cc  mov     rcx, [rcx+38h]; Object
0x1400178d0  test    rcx, rcx
0x1400178d3  jz      short loc_1400178E6
0x1400178d5  mov     edx, 6661754Ch; Tag
0x1400178da  call    cs:__imp_ObfDereferenceObjectWithTag
0x1400178e1  nop     dword ptr [rax+rax+00h]
0x1400178e6  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x1400178eb  lea     rdi, [rbx+0B8h]
0x1400178f2  test    eax, eax
0x1400178f4  jz      short loc_14001792D
0x1400178f6  mov     rcx, [rdi]; Handle
0x1400178f9  test    rcx, rcx
0x1400178fc  jz      short loc_140017911
0x1400178fe  call    cs:__imp_ZwClose
0x140017905  nop     dword ptr [rax+rax+00h]
0x14001790a  mov     qword ptr [rdi], 0
0x140017911  mov     rcx, [rbx+0B0h]
0x140017918  test    rcx, rcx
0x14001791b  jz      short loc_14001792D
0x14001791d  call    LuafvDereferenceUser
0x140017922  mov     qword ptr [rbx+0B0h], 0
0x14001792d  mov     rcx, [rbx+48h]
0x140017931  test    rcx, rcx
0x140017934  jz      short loc_140017942
0x140017936  call    LuafvFreePool
0x14001793b  xorps   xmm0, xmm0
0x14001793e  movups  xmmword ptr [rbx+40h], xmm0
0x140017942  call    Feature_ShadowAdminAppCompat__private_IsEnabledDeviceUsageNoInline
0x140017947  test    eax, eax
0x140017949  jz      short loc_140017993
0x14001794b  mov     rcx, [rbx+80h]
0x140017952  test    rcx, rcx
0x140017955  jz      short loc_140017963
0x140017957  call    LuafvFreePool
0x14001795c  xorps   xmm0, xmm0
0x14001795f  movups  xmmword ptr [rbx+78h], xmm0
0x140017963  mov     rcx, [rbx+70h]
0x140017967  test    rcx, rcx
0x14001796a  jz      short loc_140017978
0x14001796c  call    LuafvFreePool
0x140017971  xorps   xmm0, xmm0
0x140017974  movups  xmmword ptr [rbx+68h], xmm0
0x140017978  mov     rcx, [rdi]; Handle
0x14001797b  test    rcx, rcx
0x14001797e  jz      short loc_140017993
0x140017980  call    cs:__imp_ZwClose
0x140017987  nop     dword ptr [rax+rax+00h]
0x14001798c  mov     qword ptr [rdi], 0
0x140017993  mov     rcx, rbx
0x140017996  call    LuafvFreePool
0x14001799b  mov     rbx, [rsp+28h+arg_0]
0x1400179a0  add     rsp, 20h
0x1400179a4  pop     rdi
0x1400179a5  retn
```
