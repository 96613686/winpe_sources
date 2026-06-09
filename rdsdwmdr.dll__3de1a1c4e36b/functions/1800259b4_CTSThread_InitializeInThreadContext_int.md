# CTSThread::InitializeInThreadContext(int)

- ea: `0x1800259b4`
- end: `0x180025a4a`
- name: `?InitializeInThreadContext@CTSThread@@AEAAJH@Z`
- size: `150`
- prototype: `__int64 __fastcall(CTSThread *this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800234e0`
- `0x180027150`

## callees

- `0x18001d114`
- `0x18001f03c`
- `0x18001f298`
- `0x1800259b4`
- `0x18002a1c4`

## string_xrefs

- `0x1800259f9`: `Failed to create thread signal event`

## pseudocode

```c
__int64 __fastcall CTSThread::InitializeInThreadContext(CTSThread *this)
{
  _QWORD *v1; // rbx
  __int64 v2; // rdx
  int v3; // edi
  __int64 v4; // r8
  __int64 v5; // r9
  int ActivityIdPrefix; // eax
  int v8; // [rsp+28h] [rbp-10h]

  v1 = (_QWORD *)((char *)this + 688);
  v3 = PAL_System_CondAlloc(0);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v2, v4, v5);
      v8 = v3;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)&WPP_903e1551464439edae082eb88b6439cd_Traceguids,
        ActivityIdPrefix,
        (__int64)"Failed to create thread signal event",
        v8);
    }
    if ( *v1 != -1 )
    {
      PAL_System_HandleFree(*v1);
      *v1 = -1;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800259b4  mov     [rsp+arg_0], rbx
0x1800259b9  push    rdi
0x1800259ba  sub     rsp, 30h
0x1800259be  lea     rbx, [rcx+2B0h]
0x1800259c5  xor     ecx, ecx; bManualReset
0x1800259c7  mov     rdx, rbx
0x1800259ca  call    PAL_System_CondAlloc
0x1800259cf  mov     edi, eax
0x1800259d1  test    eax, eax
0x1800259d3  jns     short loc_180025A3D
0x1800259d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800259dc  lea     rax, WPP_GLOBAL_Control
0x1800259e3  cmp     rcx, rax
0x1800259e6  jz      short loc_180025A28
0x1800259e8  test    byte ptr [rcx+1Ch], 8
0x1800259ec  jz      short loc_180025A28
0x1800259ee  cmp     byte ptr [rcx+19h], 2
0x1800259f2  jb      short loc_180025A28
0x1800259f4  call    RdpX_GetActivityIdPrefix
0x1800259f9  lea     rcx, aFailedToCreate_1; "Failed to create thread signal event"
0x180025a00  mov     [rsp+38h+var_10], edi
0x180025a04  mov     [rsp+38h+var_18], rcx
0x180025a09  lea     r8, WPP_903e1551464439edae082eb88b6439cd_Traceguids
0x180025a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a17  mov     edx, 2Dh ; '-'
0x180025a1c  mov     r9d, eax
0x180025a1f  mov     rcx, [rcx+10h]
0x180025a23  call    WPP_SF_DsD
0x180025a28  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180025a2c  jz      short loc_180025A3D
0x180025a2e  mov     rcx, [rbx]
0x180025a31  call    PAL_System_HandleFree
0x180025a36  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180025a3d  mov     rbx, [rsp+38h+arg_0]
0x180025a42  mov     eax, edi
0x180025a44  add     rsp, 30h
0x180025a48  pop     rdi
0x180025a49  retn
```
