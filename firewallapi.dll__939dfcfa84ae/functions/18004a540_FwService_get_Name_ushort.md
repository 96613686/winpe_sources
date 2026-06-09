# FwService::get_Name(ushort * *)

- ea: `0x18004a540`
- end: `0x18004a5d1`
- name: `?get_Name@FwService@@UEAAJPEAPEAG@Z`
- size: `145`
- prototype: `__int64 __fastcall(FwService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18004a540`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004a574`
- `OLEAUT32!__imp_SysAllocString` at `0x18004a574`
- `fwbase!FwReportErrorAsWinError` at `0x18004a59a`
- `fwbase!FwReportErrorAsWinError` at `0x18004a59a`
- `fwbase!FwReportReturnError` at `0x18004a560`
- `fwbase!FwReportReturnError` at `0x18004a5b5`
- `fwbase!FwReportReturnError` at `0x18004a560`
- `fwbase!FwReportReturnError` at `0x18004a5b5`

## string_xrefs

- `0x18004a557`: `FwService::get_Name`
- `0x18004a593`: `FwService::get_Name`
- `0x18004a5ae`: `FwService::get_Name`

## pseudocode

```c
__int64 __fastcall FwService::get_Name(const OLECHAR **this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rax

  if ( !a2 )
  {
    v3 = -2147467261;
    FwReportReturnError("FwService::get_Name", 2147500035LL);
    return (unsigned int)FwReportReturnError("FwService::get_Name", v3);
  }
  v3 = 0;
  v4 = SysAllocString(this[4]);
  *a2 = v4;
  if ( !v4 )
  {
    v3 = FwReportErrorAsWinError("FwService::get_Name", "SysAllocString", 8);
    if ( (v3 & 0x80000000) != 0 )
      return (unsigned int)FwReportReturnError("FwService::get_Name", v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18004a540  mov     [rsp+arg_0], rbx
0x18004a545  push    rdi
0x18004a546  sub     rsp, 20h
0x18004a54a  mov     rdi, rdx
0x18004a54d  test    rdx, rdx
0x18004a550  jnz     short loc_18004A56E
0x18004a552  mov     ebx, 80004003h
0x18004a557  lea     rcx, aFwserviceGetNa; "FwService::get_Name"
0x18004a55e  mov     edx, ebx
0x18004a560  call    cs:__imp_FwReportReturnError
0x18004a567  nop     dword ptr [rax+rax+00h]
0x18004a56c  jmp     short loc_18004A5AC
0x18004a56e  mov     rcx, [rcx+20h]; psz
0x18004a572  xor     ebx, ebx
0x18004a574  call    cs:__imp_SysAllocString
0x18004a57b  nop     dword ptr [rax+rax+00h]
0x18004a580  mov     [rdi], rax
0x18004a583  test    rax, rax
0x18004a586  jnz     short loc_18004A5C3
0x18004a588  lea     r8d, [rbx+8]
0x18004a58c  lea     rdx, aSysallocstring; "SysAllocString"
0x18004a593  lea     rcx, aFwserviceGetNa; "FwService::get_Name"
0x18004a59a  call    cs:__imp_FwReportErrorAsWinError
0x18004a5a1  nop     dword ptr [rax+rax+00h]
0x18004a5a6  mov     ebx, eax
0x18004a5a8  test    eax, eax
0x18004a5aa  jns     short loc_18004A5C3
0x18004a5ac  mov     edx, ebx
0x18004a5ae  lea     rcx, aFwserviceGetNa; "FwService::get_Name"
0x18004a5b5  call    cs:__imp_FwReportReturnError
0x18004a5bc  nop     dword ptr [rax+rax+00h]
0x18004a5c1  mov     ebx, eax
0x18004a5c3  mov     eax, ebx
0x18004a5c5  mov     rbx, [rsp+28h+arg_0]
0x18004a5ca  add     rsp, 20h
0x18004a5ce  pop     rdi
0x18004a5cf  retn
```
