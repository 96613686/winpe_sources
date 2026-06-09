# CleanupMgrTelemetry::CleanmgrPluginInstantiate::Stop(ushort const *,_GUID,double,long)

- ea: `0x14001097c`
- end: `0x1400109f9`
- name: `?Stop@CleanmgrPluginInstantiate@CleanupMgrTelemetry@@QEAAXPEBGU_GUID@@NJ@Z`
- size: `125`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanmgrPluginInstantiate *this, const unsigned __int16 *, struct _GUID *, double, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013530`

## callees

- `0x14001097c`
- `0x1400166a4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001098d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001098d`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanmgrPluginInstantiate::Stop(
        CleanupMgrTelemetry::CleanmgrPluginInstantiate *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        double a4,
        char a5)
{
  int v5; // ebx
  ULONGLONG TickCount64; // rax
  int v7; // edx
  int v8; // r8d
  int v9; // ecx
  double v10; // xmm0_8
  double v11; // xmm0_8

  v5 = (int)a2;
  TickCount64 = GetTickCount64();
  if ( (Microsoft_Windows_CleanmgrEnableBits & 1) != 0 )
  {
    v9 = TickCount64 - cleanmgrBeforePluginInstantiationTick;
    if ( (__int64)(TickCount64 - cleanmgrBeforePluginInstantiationTick) < 0 )
    {
      v9 &= 1u;
      v10 = (double)(int)(v9 | ((TickCount64 - cleanmgrBeforePluginInstantiationTick) >> 1))
          + (double)(int)(v9 | ((TickCount64 - cleanmgrBeforePluginInstantiationTick) >> 1));
    }
    else
    {
      v10 = (double)v9;
    }
    v11 = v10 / 1000.0;
    McTemplateU0qzggd_EventWriteTransfer(v9, v7, v8, v5, SLOBYTE(v11), SLOBYTE(a4), a5);
  }
}

```

## disassembly

```asm
0x14001097c  push    rbx
0x14001097e  sub     rsp, 50h
0x140010982  movaps  [rsp+58h+var_18], xmm6
0x140010987  mov     rbx, rdx
0x14001098a  movaps  xmm6, xmm3
0x14001098d  call    cs:__imp_GetTickCount64
0x140010993  test    cs:Microsoft_Windows_CleanmgrEnableBits, 1
0x14001099a  mov     rcx, rax
0x14001099d  jz      short loc_1400109EE
0x14001099f  sub     rcx, cs:?cleanmgrBeforePluginInstantiationTick@@3_KA; unsigned __int64 cleanmgrBeforePluginInstantiationTick
0x1400109a6  xorps   xmm0, xmm0
0x1400109a9  js      short loc_1400109B2
0x1400109ab  cvtsi2sd xmm0, rcx
0x1400109b0  jmp     short loc_1400109C7
0x1400109b2  mov     rax, rcx
0x1400109b5  and     ecx, 1
0x1400109b8  shr     rax, 1
0x1400109bb  or      rax, rcx
0x1400109be  cvtsi2sd xmm0, rax
0x1400109c3  addsd   xmm0, xmm0
0x1400109c7  divsd   xmm0, cs:__real@408f400000000000
0x1400109cf  mov     eax, [rsp+58h+arg_20]
0x1400109d6  mov     r9, rbx
0x1400109d9  mov     [rsp+58h+var_28], eax
0x1400109dd  movsd   [rsp+58h+var_30], xmm6
0x1400109e3  movsd   [rsp+58h+var_38], xmm0
0x1400109e9  call    McTemplateU0qzggd_EventWriteTransfer
0x1400109ee  movaps  xmm6, [rsp+58h+var_18]
0x1400109f3  add     rsp, 50h
0x1400109f7  pop     rbx
0x1400109f8  retn
```
