# StartMeasuringTimeForAuth

- ea: `0x18001a920`
- end: `0x18001a9bb`
- name: `StartMeasuringTimeForAuth`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800233c0`

## callees

- `0x180004f40`
- `0x180005440`
- `0x18001a920`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a95e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001a95e`

## pseudocode

```c
int __fastcall StartMeasuringTimeForAuth(__int64 a1)
{
  int result; // eax
  __int64 v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
  result = GetTickCount();
  *(_DWORD *)(a1 + 2420) = result;
  if ( (byte_18003DF42 & 1) != 0 )
    result = McTemplateU0q_EtwEventWriteTransfer(v3, (__int64)AuthPerfStart, *(unsigned int *)(a1 + 20));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    return WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x18001a920  mov     [rsp+arg_0], rbx
0x18001a925  push    rsi
0x18001a926  sub     rsp, 20h
0x18001a92a  mov     rbx, rcx
0x18001a92d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a934  lea     rsi, WPP_GLOBAL_Control
0x18001a93b  cmp     rcx, rsi
0x18001a93e  jz      short loc_18001A95E
0x18001a940  test    dword ptr [rcx+44h], 800h
0x18001a947  jz      short loc_18001A95E
0x18001a949  mov     rcx, [rcx+38h]
0x18001a94d  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18001a954  mov     edx, 2Fh ; '/'
0x18001a959  call    WPP_SF_
0x18001a95e  call    cs:__imp_GetTickCount
0x18001a964  mov     [rbx+974h], eax
0x18001a96a  test    cs:byte_18003DF42, 1
0x18001a971  jz      short loc_18001A983
0x18001a973  mov     r8d, [rbx+14h]
0x18001a977  lea     rdx, AuthPerfStart
0x18001a97e  call    McTemplateU0q_EtwEventWriteTransfer
0x18001a983  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a98a  cmp     rcx, rsi
0x18001a98d  jz      short loc_18001A9B0
0x18001a98f  test    dword ptr [rcx+44h], 800h
0x18001a996  jz      short loc_18001A9B0
0x18001a998  mov     rcx, [rcx+38h]
0x18001a99c  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18001a9a3  mov     edx, 30h ; '0'
0x18001a9a8  xor     r9d, r9d
0x18001a9ab  call    WPP_SF_D
0x18001a9b0  mov     rbx, [rsp+28h+arg_0]
0x18001a9b5  add     rsp, 20h
0x18001a9b9  pop     rsi
0x18001a9ba  retn
```
