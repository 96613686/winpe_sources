# InteractivityUIPage::GetUserChoices(tagSAFEARRAY * *)

- ea: `0x14002b480`
- end: `0x14002b598`
- name: `?GetUserChoices@InteractivityUIPage@@MEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(InteractivityUIPage *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140020420`
- `0x14002b480`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14002b4c7`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b4c7`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b576`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b576`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b50f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b50f`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b556`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b556`

## pseudocode

```c
__int64 __fastcall InteractivityUIPage::GetUserChoices(InteractivityUIPage *this, struct tagSAFEARRAY **a2)
{
  const OLECHAR *v4; // rcx
  BSTR v5; // rsi
  unsigned int v6; // ebx
  SAFEARRAY *v7; // rax
  struct tagSAFEARRAY *v8; // rdi
  HRESULT v9; // eax
  int v10; // r9d
  LONG rgIndices; // [rsp+50h] [rbp+8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp+18h] BYREF

  rgIndices = 0;
  rgsabound = (SAFEARRAYBOUND)1LL;
  v4 = L"Run";
  if ( !*((_DWORD *)this + 52) )
    v4 = L"NotRun";
  v5 = SysAllocString(v4);
  if ( v5 )
  {
    v7 = SafeArrayCreate(8u, 1u, &rgsabound);
    v8 = v7;
    if ( v7 )
    {
      v9 = SafeArrayPutElement(v7, &rgIndices, v5);
      v6 = v9;
      if ( v9 >= 0 )
      {
        *a2 = v8;
        goto LABEL_11;
      }
      v10 = 4192;
    }
    else
    {
      v9 = -2147024882;
      v10 = 4189;
      v6 = -2147024882;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityUIPage::GetUserChoices", v10, v9);
LABEL_11:
    SysFreeString(v5);
    return v6;
  }
  v6 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityUIPage::GetUserChoices", 4186, -2147024882);
  return v6;
}

```

## disassembly

```asm
0x14002b480  mov     [rsp+arg_8], rbx
0x14002b485  mov     [rsp+arg_18], rbp
0x14002b48a  push    rsi
0x14002b48b  push    rdi
0x14002b48c  push    r14
0x14002b48e  sub     rsp, 30h
0x14002b492  mov     rax, rcx
0x14002b495  mov     [rsp+48h+rgIndices], 0
0x14002b49d  mov     r14, rdx
0x14002b4a0  mov     qword ptr [rsp+48h+rgsabound.cElements], 1
0x14002b4a9  lea     rdx, aNotrun; "NotRun"
0x14002b4b0  mov     ebp, 1
0x14002b4b5  lea     rcx, aRun; "Run"
0x14002b4bc  cmp     dword ptr [rax+0D0h], 0
0x14002b4c3  cmovz   rcx, rdx; psz
0x14002b4c7  call    cs:__imp_SysAllocString
0x14002b4ce  nop     dword ptr [rax+rax+00h]
0x14002b4d3  mov     rsi, rax
0x14002b4d6  test    rax, rax
0x14002b4d9  jnz     short loc_14002B503
0x14002b4db  mov     eax, 8007000Eh
0x14002b4e0  lea     r8, aInteractivityu_3; "InteractivityUIPage::GetUserChoices"
0x14002b4e7  mov     r9d, 105Ah
0x14002b4ed  mov     [rsp+48h+var_28], eax
0x14002b4f1  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b4f8  mov     ecx, ebp; Level
0x14002b4fa  mov     ebx, eax
0x14002b4fc  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b501  jmp     short loc_14002B582
0x14002b503  mov     ecx, 8; vt
0x14002b508  lea     r8, [rsp+48h+rgsabound]; rgsabound
0x14002b50d  mov     edx, ebp; cDims
0x14002b50f  call    cs:__imp_SafeArrayCreate
0x14002b516  nop     dword ptr [rax+rax+00h]
0x14002b51b  mov     rdi, rax
0x14002b51e  test    rax, rax
0x14002b521  jnz     short loc_14002B54B
0x14002b523  mov     eax, 8007000Eh
0x14002b528  mov     r9d, 105Dh
0x14002b52e  mov     ebx, eax
0x14002b530  lea     r8, aInteractivityu_3; "InteractivityUIPage::GetUserChoices"
0x14002b537  mov     [rsp+48h+var_28], eax
0x14002b53b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b542  mov     ecx, ebp; Level
0x14002b544  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b549  jmp     short loc_14002B573
0x14002b54b  mov     r8, rsi; pv
0x14002b54e  lea     rdx, [rsp+48h+rgIndices]; rgIndices
0x14002b553  mov     rcx, rdi; psa
0x14002b556  call    cs:__imp_SafeArrayPutElement
0x14002b55d  nop     dword ptr [rax+rax+00h]
0x14002b562  mov     ebx, eax
0x14002b564  test    eax, eax
0x14002b566  jns     short loc_14002B570
0x14002b568  mov     r9d, 1060h
0x14002b56e  jmp     short loc_14002B530
0x14002b570  mov     [r14], rdi
0x14002b573  mov     rcx, rsi; bstrString
0x14002b576  call    cs:__imp_SysFreeString
0x14002b57d  nop     dword ptr [rax+rax+00h]
0x14002b582  mov     rbp, [rsp+48h+arg_18]
0x14002b587  mov     eax, ebx
0x14002b589  mov     rbx, [rsp+48h+arg_8]
0x14002b58e  add     rsp, 30h
0x14002b592  pop     r14
0x14002b594  pop     rdi
0x14002b595  pop     rsi
0x14002b596  retn
```
