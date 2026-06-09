# GetCertificationUrlFromRegistryOrAD(ushort * *)

- ea: `0x1800262b4`
- end: `0x1800262f8`
- name: `?GetCertificationUrlFromRegistryOrAD@@YAJPEAPEAG@Z`
- size: `68`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026568`

## callees

- `0x1800046c8`
- `0x180025a10`
- `0x1800262b4`
- `0x180039970`

## string_xrefs

- `0x1800262e1`: `[msdrm]: GetActiveDirectoryService FAILED : %x `
- `0x1800262bd`: `SOFTWARE\Microsoft\MSDRM\ServiceLocation\Activation`

## pseudocode

```c
__int64 __fastcall GetCertificationUrlFromRegistryOrAD(unsigned __int16 **a1)
{
  __int64 result; // rax

  result = GetRegistryKey((HKEY)a1, L"SOFTWARE\\Microsoft\\MSDRM\\ServiceLocation\\Activation", 0, a1);
  if ( (int)result < 0 )
  {
    result = GetActiveDirectoryService(a1);
    if ( (int)result < 0 )
    {
      _RTLTRACE("[msdrm]: GetActiveDirectoryService FAILED : %x ", result);
      return 2147798856LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800262b4  push    rbx
0x1800262b6  sub     rsp, 20h
0x1800262ba  mov     r9, rcx; unsigned __int16 **
0x1800262bd  lea     rdx, ?g_wszSD_ActivationKey@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\ServiceLoca"...
0x1800262c4  xor     r8d, r8d; unsigned __int16 *
0x1800262c7  mov     rbx, rcx
0x1800262ca  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; GetRegistryKey(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800262cf  test    eax, eax
0x1800262d1  jns     short loc_1800262F2
0x1800262d3  mov     rcx, rbx; unsigned __int16 **
0x1800262d6  call    ?GetActiveDirectoryService@@YAJPEAPEAG@Z; GetActiveDirectoryService(ushort * *)
0x1800262db  test    eax, eax
0x1800262dd  jns     short loc_1800262F2
0x1800262df  mov     edx, eax
0x1800262e1  lea     rcx, aMsdrmGetactive; "[msdrm]: GetActiveDirectoryService FAIL"...
0x1800262e8  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800262ed  mov     eax, 8004CF48h
0x1800262f2  add     rsp, 20h
0x1800262f6  pop     rbx
0x1800262f7  retn
```
