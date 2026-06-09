# CTSBufferResult::Initialize(void)

- ea: `0x180029a70`
- end: `0x180029ae8`
- name: `?Initialize@CTSBufferResult@@UEAAJXZ`
- size: `120`
- prototype: `__int64 __fastcall(CTSBufferResult *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180025a50`

## callees

- `0x18001d114`
- `0x180029978`
- `0x180029a70`
- `0x18002a1c4`

## string_xrefs

- `0x180029ab1`: `Failed to create default buffer result buffer!`

## pseudocode

```c
__int64 __fastcall CTSBufferResult::Initialize(CTSBufferResult *this)
{
  __int64 v1; // rdx
  int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // r9
  int ActivityIdPrefix; // eax
  int v7; // [rsp+28h] [rbp-10h]

  v2 = CTSBufferResult::Initialize((CTSBufferResult *)((char *)this - 8), 0x400u, 0);
  if ( v2 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v1, v3, v4);
    v7 = v2;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)WPP_45c8207700f83d40fa4666bbba92ada0_Traceguids,
      ActivityIdPrefix,
      (__int64)"Failed to create default buffer result buffer!",
      v7);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180029a70  push    rbx
0x180029a72  sub     rsp, 30h
0x180029a76  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180029a7a  xor     r8d, r8d; void *
0x180029a7d  mov     edx, 400h; unsigned int
0x180029a82  call    ?Initialize@CTSBufferResult@@IEAAJKPEAX@Z; CTSBufferResult::Initialize(ulong,void *)
0x180029a87  mov     ebx, eax
0x180029a89  test    eax, eax
0x180029a8b  jns     short loc_180029AE0
0x180029a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a94  lea     rax, WPP_GLOBAL_Control
0x180029a9b  cmp     rcx, rax
0x180029a9e  jz      short loc_180029AE0
0x180029aa0  test    byte ptr [rcx+1Ch], 8
0x180029aa4  jz      short loc_180029AE0
0x180029aa6  cmp     byte ptr [rcx+19h], 2
0x180029aaa  jb      short loc_180029AE0
0x180029aac  call    RdpX_GetActivityIdPrefix
0x180029ab1  lea     rcx, aFailedToCreate_3; "Failed to create default buffer result "...
0x180029ab8  mov     [rsp+38h+var_10], ebx
0x180029abc  mov     [rsp+38h+var_18], rcx
0x180029ac1  lea     r8, WPP_45c8207700f83d40fa4666bbba92ada0_Traceguids
0x180029ac8  mov     rcx, cs:WPP_GLOBAL_Control
0x180029acf  mov     edx, 2Ah ; '*'
0x180029ad4  mov     r9d, eax
0x180029ad7  mov     rcx, [rcx+10h]
0x180029adb  call    WPP_SF_DsD
0x180029ae0  mov     eax, ebx
0x180029ae2  add     rsp, 30h
0x180029ae6  pop     rbx
0x180029ae7  retn
```
