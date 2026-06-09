# PwrshPlugInMediator::ReportError(_WSMAN_PLUGIN_REQUEST *,ulong,...)

- ea: `0x180004050`
- end: `0x1800040c8`
- name: `?ReportError@PwrshPlugInMediator@@AEAAKPEAU_WSMAN_PLUGIN_REQUEST@@KZZ`
- size: `120`
- prototype: `__int64(PwrshPlugInMediator *this, struct _WSMAN_PLUGIN_REQUEST *, DWORD, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180002560`
- `0x180002980`
- `0x180002a18`
- `0x180002a88`
- `0x180004138`
- `0x1800041b8`

## callees

- `0x180002e80`
- `0x180004050`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800040ba`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800040ba`
- `WsmSvc!WSManPluginOperationComplete` at `0x1800040a5`
- `WsmSvc!WSManPluginOperationComplete` at `0x1800040a5`

## pseudocode

```c
__int64 PwrshPlugInMediator::ReportError(PwrshPlugInMediator *this, struct _WSMAN_PLUGIN_REQUEST *a2, DWORD a3, ...)
{
  DWORD v4; // ebx
  PCWSTR extendedInformation; // [rsp+20h] [rbp-18h] BYREF
  va_list v7; // [rsp+28h] [rbp-10h] BYREF
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  va_copy(v7, va);
  extendedInformation = 0;
  GetFormattedErrorMessage((unsigned __int16 **)&extendedInformation, a3, &v7);
  v7 = 0;
  v4 = WSManPluginOperationComplete(a2, 0, a3, extendedInformation);
  if ( extendedInformation )
    operator delete[]((void *)extendedInformation);
  return v4;
}

```

## disassembly

```asm
0x180004050  mov     r11, rsp
0x180004053  mov     [r11+18h], r8d
0x180004057  mov     [r11+20h], r9
0x18000405b  push    rbx
0x18000405c  sub     rsp, 30h
0x180004060  lea     rcx, [r11+20h]
0x180004064  mov     qword ptr [r11-10h], 0
0x18000406c  mov     eax, r8d
0x18000406f  mov     [r11-10h], rcx
0x180004073  mov     rbx, rdx
0x180004076  mov     qword ptr [r11-18h], 0
0x18000407e  lea     rcx, [r11-18h]; unsigned __int16 **
0x180004082  mov     edx, eax; unsigned int
0x180004084  lea     r8, [r11-10h]
0x180004088  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x18000408d  mov     r9, [rsp+38h+extendedInformation]; extendedInformation
0x180004092  xor     edx, edx; flags
0x180004094  mov     r8d, [rsp+38h+errorCode]; errorCode
0x180004099  mov     rcx, rbx; requestDetails
0x18000409c  mov     [rsp+38h+var_10], 0
0x1800040a5  call    cs:__imp_WSManPluginOperationComplete
0x1800040ab  cmp     [rsp+38h+extendedInformation], 0
0x1800040b1  mov     ebx, eax
0x1800040b3  jz      short loc_1800040C0
0x1800040b5  mov     rcx, [rsp+38h+extendedInformation]
0x1800040ba  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800040c0  mov     eax, ebx
0x1800040c2  add     rsp, 30h
0x1800040c6  pop     rbx
0x1800040c7  retn
```
