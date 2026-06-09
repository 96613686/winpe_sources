# ActiveScriptError::Free(void)

- ea: `0x1801d492c`
- end: `0x1801d4a67`
- name: `?Free@ActiveScriptError@@AEAAXXZ`
- size: `315`
- prototype: `void __fastcall(ActiveScriptError *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1801d39d0`

## callees

- `0x1800e0af8`
- `0x18013674c`
- `0x1801d492c`
- `0x1801d4a70`
- `0x180364010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d494b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1801d494b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d4975`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d49ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d49cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d49f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d4975`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d49ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d49cf`
- `OLEAUT32!__imp_SysFreeString` at `0x1801d49f2`

## pseudocode

```c
void __fastcall ActiveScriptError::Free(ActiveScriptError *this)
{
  ActiveScriptError *v2; // rcx
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  __int64 v7; // rcx
  char *v8; // rdx

  FreeExcepInfo((struct tagEXCEPINFO *)((char *)this + 56));
  CoTaskMemFree(*((LPVOID *)this + 17));
  ActiveScriptError::FreeStackTrace(v2, (ActiveScriptError *)((char *)this + 144));
  v3 = (OLECHAR *)*((_QWORD *)this + 30);
  *((_QWORD *)this + 17) = 0;
  SysFreeString(v3);
  v4 = (OLECHAR *)*((_QWORD *)this + 21);
  *((_QWORD *)this + 27) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_DWORD *)this + 57) = -1;
  if ( v4 )
  {
    SysFreeString(v4);
    *((_QWORD *)this + 21) = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 20);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 20) = 0;
  }
  v6 = (OLECHAR *)*((_QWORD *)this + 22);
  if ( v6 )
  {
    SysFreeString(v6);
    *((_QWORD *)this + 22) = 0;
  }
  v7 = *((_QWORD *)this + 23);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 23) = 0;
  }
  v8 = (char *)*((_QWORD *)this + 25);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFELL )
  {
    Recycler::RootRelease(*((Recycler **)this + 26), v8, 0);
    *((_QWORD *)this + 25) = 0;
  }
}

```

## disassembly

```asm
0x1801d492c  mov     [rsp+arg_0], rcx
0x1801d4931  push    rbx
0x1801d4932  sub     rsp, 20h
0x1801d4936  mov     rbx, [rsp+28h+arg_0]
0x1801d493b  lea     rcx, [rbx+38h]; struct tagEXCEPINFO *
0x1801d493f  call    ?FreeExcepInfo@@YAXPEAUtagEXCEPINFO@@@Z; FreeExcepInfo(tagEXCEPINFO *)
0x1801d4944  mov     rcx, [rbx+88h]; pv
0x1801d494b  call    cs:__imp_CoTaskMemFree
0x1801d4952  nop     dword ptr [rax+rax+00h]
0x1801d4957  lea     rdx, [rbx+90h]; struct CallStack *
0x1801d495e  call    ?FreeStackTrace@ActiveScriptError@@AEAAXAEAUCallStack@@@Z; ActiveScriptError::FreeStackTrace(CallStack &)
0x1801d4963  mov     rcx, [rbx+0F0h]; bstrString
0x1801d496a  mov     qword ptr [rbx+88h], 0
0x1801d4975  call    cs:__imp_SysFreeString
0x1801d497c  nop     dword ptr [rax+rax+00h]
0x1801d4981  mov     rcx, [rbx+0A8h]; bstrString
0x1801d4988  mov     qword ptr [rbx+0D8h], 0
0x1801d4993  mov     dword ptr [rbx+0E0h], 0
0x1801d499d  mov     dword ptr [rbx+0E4h], 0FFFFFFFFh
0x1801d49a7  test    rcx, rcx
0x1801d49aa  jz      short loc_1801D49C3
0x1801d49ac  call    cs:__imp_SysFreeString
0x1801d49b3  nop     dword ptr [rax+rax+00h]
0x1801d49b8  mov     qword ptr [rbx+0A8h], 0
0x1801d49c3  mov     rcx, [rbx+0A0h]; bstrString
0x1801d49ca  test    rcx, rcx
0x1801d49cd  jz      short loc_1801D49E6
0x1801d49cf  call    cs:__imp_SysFreeString
0x1801d49d6  nop     dword ptr [rax+rax+00h]
0x1801d49db  mov     qword ptr [rbx+0A0h], 0
0x1801d49e6  mov     rcx, [rbx+0B0h]; bstrString
0x1801d49ed  test    rcx, rcx
0x1801d49f0  jz      short loc_1801D4A09
0x1801d49f2  call    cs:__imp_SysFreeString
0x1801d49f9  nop     dword ptr [rax+rax+00h]
0x1801d49fe  mov     qword ptr [rbx+0B0h], 0
0x1801d4a09  mov     rcx, [rbx+0B8h]
0x1801d4a10  test    rcx, rcx
0x1801d4a13  jz      short loc_1801D4A2C
0x1801d4a15  mov     rax, [rcx]
0x1801d4a18  mov     rax, [rax+10h]
0x1801d4a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d4a21  mov     qword ptr [rbx+0B8h], 0
0x1801d4a2c  mov     rdx, [rbx+0C8h]; void *
0x1801d4a33  mov     rcx, 0FFFFFFFFFFFEh
0x1801d4a3d  lea     rax, [rdx-1]
0x1801d4a41  cmp     rax, rcx
0x1801d4a44  ja      short loc_1801D4A60
0x1801d4a46  mov     rcx, [rbx+0D0h]; this
0x1801d4a4d  xor     r8d, r8d; unsigned int *
0x1801d4a50  call    ?RootRelease@Recycler@@QEAAXPEAXPEAI@Z; Recycler::RootRelease(void *,uint *)
0x1801d4a55  mov     qword ptr [rbx+0C8h], 0
0x1801d4a60  add     rsp, 20h
0x1801d4a64  pop     rbx
0x1801d4a65  retn
```
