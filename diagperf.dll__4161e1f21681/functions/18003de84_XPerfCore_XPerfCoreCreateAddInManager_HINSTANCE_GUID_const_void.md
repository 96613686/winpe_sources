# XPerfCore::XPerfCoreCreateAddInManager(HINSTANCE__ *,_GUID const &,void * *)

- ea: `0x18003de84`
- end: `0x18003df1f`
- name: `?XPerfCoreCreateAddInManager@XPerfCore@@YAJPEAUHINSTANCE__@@AEBU_GUID@@PEAPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(XPerfCore *__hidden this, HINSTANCE, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001d2dc`
- `0x1800279d8`
- `0x180031aec`
- `0x18008ed30`
- `0x1800b67d8`
- `0x1800c895c`

## callees

- `0x18003de84`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003deb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003deb2`

## string_xrefs

- `0x18003deab`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall XPerfCore::XPerfCoreCreateAddInManager(
        XPerfCore *this,
        HINSTANCE a2,
        const struct _GUID *a3,
        void **a4)
{
  int v5; // ebx
  FARPROC ProcAddress; // rax
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  if ( this )
  {
    ProcAddress = GetProcAddress((HMODULE)this, "DllGetClassObject");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
             &GUID_fde49531_0ff3_4167_b9b9_83134ee5d5d2,
             &IID_IClassFactory,
             &v8);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, const struct _GUID *))(*(_QWORD *)v8 + 24LL))(
               v8,
               0,
               &GUID_907996dc_eb88_4806_aeb8_bf161c0d2de2,
               a3);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    return (unsigned int)-2147024890;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003de84  mov     [rsp+arg_0], rbx
0x18003de89  mov     [rsp+arg_8], rdx
0x18003de8e  push    rdi
0x18003de8f  sub     rsp, 30h
0x18003de93  mov     [rsp+38h+arg_8], 0
0x18003de9c  mov     rdi, r8
0x18003de9f  test    rcx, rcx
0x18003dea2  jnz     short loc_18003DEAB
0x18003dea4  mov     ebx, 80070006h
0x18003dea9  jmp     short loc_18003DF12
0x18003deab  lea     rdx, ProcName; "DllGetClassObject"
0x18003deb2  call    cs:__imp_GetProcAddress
0x18003deb8  test    rax, rax
0x18003debb  jnz     short loc_18003DEC4
0x18003debd  mov     ebx, 8000FFFFh
0x18003dec2  jmp     short loc_18003DF12
0x18003dec4  lea     r8, [rsp+38h+arg_8]
0x18003dec9  lea     rdx, IID_IClassFactory
0x18003ded0  lea     rcx, _GUID_fde49531_0ff3_4167_b9b9_83134ee5d5d2
0x18003ded7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dedc  mov     ebx, eax
0x18003dede  test    eax, eax
0x18003dee0  js      short loc_18003DF12
0x18003dee2  mov     rcx, [rsp+38h+arg_8]
0x18003dee7  lea     r8, _GUID_907996dc_eb88_4806_aeb8_bf161c0d2de2
0x18003deee  mov     r9, rdi
0x18003def1  xor     edx, edx
0x18003def3  mov     rax, [rcx]
0x18003def6  mov     rax, [rax+18h]
0x18003defa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003deff  mov     rcx, [rsp+38h+arg_8]
0x18003df04  mov     ebx, eax
0x18003df06  mov     rax, [rcx]
0x18003df09  mov     rax, [rax+10h]
0x18003df0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df12  mov     eax, ebx
0x18003df14  mov     rbx, [rsp+38h+arg_0]
0x18003df19  add     rsp, 30h
0x18003df1d  pop     rdi
0x18003df1e  retn
```
