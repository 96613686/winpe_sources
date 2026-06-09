# TransformSleepStudyReport

- ea: `0x180077ec0`
- end: `0x180077f27`
- name: `TransformSleepStudyReport`
- size: `103`
- prototype: `__int64 __fastcall(unsigned __int16 *, wchar_t *FileName)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180049ae4`
- `0x18005f0fc`
- `0x180077ec0`
- `0x18007b860`

## import_xrefs

- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180077eef`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x180077eef`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180077f0f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180077f0f`

## string_xrefs

- `0x180077efe`: `res://energy.dll/IDR_XML_SLEEPSTUDY_TRANSFORM`

## pseudocode

```c
__int64 __fastcall TransformSleepStudyReport(unsigned __int16 *a1, wchar_t *FileName)
{
  HRESULT v4; // ebx

  if ( StringEndsWith(a1, FileName) )
  {
    return (unsigned int)SleepstudyJsonReporter::TransformReport(a1, FileName);
  }
  else
  {
    v4 = CoInitialize(0);
    if ( v4 >= 0 )
    {
      v4 = PerformXslTransform(L"res://energy.dll/IDR_XML_SLEEPSTUDY_TRANSFORM", a1, FileName);
      CoUninitialize();
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180077ec0  mov     [rsp+arg_0], rbx
0x180077ec5  mov     [rsp+arg_8], rsi
0x180077eca  push    rdi
0x180077ecb  sub     rsp, 20h
0x180077ecf  mov     rsi, rdx
0x180077ed2  mov     rdi, rcx
0x180077ed5  call    ?StringEndsWith@@YAEPEBG0@Z; StringEndsWith(ushort const *,ushort const *)
0x180077eda  test    al, al
0x180077edc  jz      short loc_180077EED
0x180077ede  mov     rdx, rsi; unsigned __int16 *
0x180077ee1  mov     rcx, rdi; unsigned __int16 *
0x180077ee4  call    ?TransformReport@SleepstudyJsonReporter@@SAJPEBG0@Z; SleepstudyJsonReporter::TransformReport(ushort const *,ushort const *)
0x180077ee9  mov     ebx, eax
0x180077eeb  jmp     short loc_180077F15
0x180077eed  xor     ecx, ecx; pvReserved
0x180077eef  call    cs:__imp_CoInitialize
0x180077ef5  mov     ebx, eax
0x180077ef7  test    eax, eax
0x180077ef9  js      short loc_180077F15
0x180077efb  mov     r8, rsi; FileName
0x180077efe  lea     rcx, aResEnergyDllId_0; "res://energy.dll/IDR_XML_SLEEPSTUDY_TRA"...
0x180077f05  mov     rdx, rdi; unsigned __int16 *
0x180077f08  call    ?PerformXslTransform@@YAJPEBG00@Z; PerformXslTransform(ushort const *,ushort const *,ushort const *)
0x180077f0d  mov     ebx, eax
0x180077f0f  call    cs:__imp_CoUninitialize
0x180077f15  mov     rsi, [rsp+28h+arg_8]
0x180077f1a  mov     eax, ebx
0x180077f1c  mov     rbx, [rsp+28h+arg_0]
0x180077f21  add     rsp, 20h
0x180077f25  pop     rdi
0x180077f26  retn
```
