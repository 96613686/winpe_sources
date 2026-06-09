# lldpProtBindAdapter

- ea: `0x140011e30`
- end: `0x140012000`
- name: `lldpProtBindAdapter`
- size: `464`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003d80`
- `0x140004b00`
- `0x140011e30`
- `0x140012000`
- `0x140012790`

## import_xrefs

- `NDIS!NdisOpenAdapterEx` at `0x140011fb6`
- `NDIS!NdisOpenAdapterEx` at `0x140011fb6`

## pseudocode

```c
__int64 __fastcall lldpProtBindAdapter(__int64 a1, void *a2, __int64 a3)
{
  unsigned int v4; // r8d
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 Binding; // rax
  PVOID *v11; // rbp
  unsigned int v12; // ebx
  __int64 i; // rdi
  __int32 v14; // ecx
  __int32 v15; // ecx
  __int32 v16; // ecx
  _NDIS_OPEN_PARAMETERS OpenParameters; // [rsp+30h] [rbp-48h] BYREF
  int v18; // [rsp+90h] [rbp+18h] BYREF

  v4 = *(unsigned __int16 *)(a3 + 104);
  v18 = 0;
  memset(&OpenParameters, 0, sizeof(OpenParameters));
  if ( (_WORD)v4 != 6 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225659LL;
    v7 = v4;
    v8 = 11;
LABEL_11:
    WPP_SF_d(v6->AttachedDevice, v8, WPP_acd65dca497b3543092d0321cbce568c_Traceguids, v7);
    return 3221225659LL;
  }
  v7 = *(unsigned int *)(a3 + 140);
  if ( (_DWORD)v7 && (_DWORD)v7 != 19 && (_DWORD)v7 != 14 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225659LL;
    v8 = 12;
    goto LABEL_11;
  }
  Binding = lldpAllocateBinding(a3);
  v11 = (PVOID *)Binding;
  if ( Binding )
  {
    for ( i = *(_QWORD *)(Binding + 120); i; i = *(_QWORD *)(i + 40) )
    {
      v14 = _InterlockedExchange((volatile __int32 *)(i + 52), 2);
      if ( v14 != 5 )
      {
        v15 = v14 - 3;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 != 2 )
              continue;
          }
        }
      }
      lldpQueueChangeNotificationEx((PVOID)i);
    }
    OpenParameters.AdapterName = *(PNDIS_STRING *)(a3 + 16);
    OpenParameters.MediumArray = (PNDIS_MEDIUM)&qword_1400092B0;
    OpenParameters.FrameTypeArray = (PNET_FRAME_TYPE)&dword_1400092AC;
    OpenParameters.SelectedMediumIndex = (PUINT)&v18;
    OpenParameters.Header = (NDIS_OBJECT_HEADER)3408263;
    OpenParameters.MediumArraySize = 1;
    OpenParameters.FrameTypeArraySize = 1;
    v12 = NdisOpenAdapterEx(WPP_MAIN_CB.Queue.ListEntry.Flink, v11, &OpenParameters, a2, v11 + 1);
    if ( v12 != 259 )
      lldpProtOpenAdapterComplete(v11);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v12;
}

```

## disassembly

```asm
0x140011e30  mov     [rsp+arg_18], rbx
0x140011e35  push    rsi
0x140011e36  sub     rsp, 70h
0x140011e3a  xor     eax, eax
0x140011e3c  xorps   xmm0, xmm0
0x140011e3f  mov     qword ptr [rsp+78h+OpenParameters.FrameTypeArraySize], rax
0x140011e44  mov     rbx, r8
0x140011e47  movzx   r8d, word ptr [r8+68h]
0x140011e4c  mov     rsi, rdx
0x140011e4f  mov     [rsp+78h+arg_10], eax
0x140011e56  mov     eax, 6
0x140011e5b  movups  xmmword ptr [rsp+78h+OpenParameters.Header.Type], xmm0
0x140011e60  movups  xmmword ptr [rsp+78h+OpenParameters.MediumArray], xmm0
0x140011e65  movups  xmmword ptr [rsp+78h+OpenParameters.SelectedMediumIndex], xmm0
0x140011e6a  cmp     ax, r8w
0x140011e6e  jz      short loc_140011E93
0x140011e70  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e77  lea     rax, WPP_GLOBAL_Control
0x140011e7e  cmp     rcx, rax
0x140011e81  jz      short loc_140011ED9
0x140011e83  cmp     byte ptr [rcx+29h], 2
0x140011e87  jb      short loc_140011ED9
0x140011e89  mov     r9d, r8d
0x140011e8c  mov     edx, 0Bh
0x140011e91  jmp     short loc_140011EC9
0x140011e93  mov     r9d, [rbx+8Ch]
0x140011e9a  test    r9d, r9d
0x140011e9d  jz      short loc_140011EED
0x140011e9f  cmp     r9d, 13h
0x140011ea3  jz      short loc_140011EED
0x140011ea5  cmp     r9d, 0Eh
0x140011ea9  jz      short loc_140011EED
0x140011eab  mov     rcx, cs:WPP_GLOBAL_Control
0x140011eb2  lea     rax, WPP_GLOBAL_Control
0x140011eb9  cmp     rcx, rax
0x140011ebc  jz      short loc_140011ED9
0x140011ebe  cmp     byte ptr [rcx+29h], 2
0x140011ec2  jb      short loc_140011ED9
0x140011ec4  mov     edx, 0Ch
0x140011ec9  mov     rcx, [rcx+18h]
0x140011ecd  lea     r8, WPP_acd65dca497b3543092d0321cbce568c_Traceguids
0x140011ed4  call    WPP_SF_d
0x140011ed9  mov     eax, 0C00000BBh
0x140011ede  mov     rbx, [rsp+78h+arg_18]
0x140011ee6  add     rsp, 70h
0x140011eea  pop     rsi
0x140011eeb  retn
0x140011eed  mov     rcx, rbx
0x140011ef0  mov     [rsp+78h+arg_0], rbp
0x140011ef8  call    lldpAllocateBinding
0x140011efd  mov     rbp, rax
0x140011f00  test    rax, rax
0x140011f03  jnz     short loc_140011F0F
0x140011f05  mov     ebx, 0C000009Ah
0x140011f0a  jmp     loc_140011FDD
0x140011f0f  mov     [rsp+78h+arg_8], rdi
0x140011f17  mov     rdi, [rax+78h]
0x140011f1b  test    rdi, rdi
0x140011f1e  jz      short loc_140011F55
0x140011f20  mov     ecx, 2
0x140011f25  xchg    ecx, [rdi+34h]
0x140011f28  cmp     ecx, 5
0x140011f2b  jz      short loc_140011F3C
0x140011f2d  sub     ecx, 3
0x140011f30  jz      short loc_140011F3C
0x140011f32  sub     ecx, 1
0x140011f35  jz      short loc_140011F3C
0x140011f37  cmp     ecx, 2
0x140011f3a  jnz     short loc_140011F4C
0x140011f3c  xor     edx, edx
0x140011f3e  mov     r8d, 80000000h
0x140011f44  mov     rcx, rdi; Context
0x140011f47  call    lldpQueueChangeNotificationEx
0x140011f4c  mov     rdi, [rdi+28h]
0x140011f50  test    rdi, rdi
0x140011f53  jnz     short loc_140011F20
0x140011f55  mov     rax, [rbx+10h]
0x140011f59  mov     [rsp+78h+OpenParameters.AdapterName], rax
0x140011f5e  lea     rax, qword_1400092B0
0x140011f65  mov     [rsp+78h+OpenParameters.MediumArray], rax
0x140011f6a  lea     rax, dword_1400092AC
0x140011f71  mov     [rsp+78h+OpenParameters.FrameTypeArray], rax
0x140011f76  lea     rax, [rsp+78h+arg_10]
0x140011f7e  mov     [rsp+78h+OpenParameters.SelectedMediumIndex], rax
0x140011f83  mov     dword ptr [rsp+78h+OpenParameters.Header.Type], 340187h
0x140011f8b  mov     [rsp+78h+OpenParameters.MediumArraySize], 1
0x140011f93  mov     [rsp+78h+OpenParameters.FrameTypeArraySize], 1
0x140011f9b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; NdisProtocolHandle
0x140011fa2  lea     rax, [rbp+8]
0x140011fa6  mov     r9, rsi; BindContext
0x140011fa9  mov     [rsp+78h+NdisBindingHandle], rax; NdisBindingHandle
0x140011fae  lea     r8, [rsp+78h+OpenParameters]; OpenParameters
0x140011fb3  mov     rdx, rbp; ProtocolBindingContext
0x140011fb6  call    cs:__imp_NdisOpenAdapterEx
0x140011fbd  nop     dword ptr [rax+rax+00h]
0x140011fc2  mov     rdi, [rsp+78h+arg_8]
0x140011fca  mov     ebx, eax
0x140011fcc  cmp     eax, 103h
0x140011fd1  jz      short loc_140011FDD
0x140011fd3  mov     edx, eax
0x140011fd5  mov     rcx, rbp; P
0x140011fd8  call    lldpProtOpenAdapterComplete
0x140011fdd  mov     rbp, [rsp+78h+arg_0]
0x140011fe5  mov     eax, ebx
0x140011fe7  mov     rbx, [rsp+78h+arg_18]
0x140011fef  add     rsp, 70h
0x140011ff3  pop     rsi
0x140011ff4  retn
```
