# GetPropertyString(IAppHostElement *,ushort const *,STBUFF *)

- ea: `0x180002428`
- end: `0x18000250a`
- name: `?GetPropertyString@@YAJPEAUIAppHostElement@@PEBGPEAVSTBUFF@@@Z`
- size: `226`
- prototype: `int(struct IAppHostElement *, const unsigned __int16 *, struct STBUFF *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002604`

## callees

- `0x180001a2c`
- `0x180002428`
- `0x180007010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002451`
- `OLEAUT32!__imp_SysAllocString` at `0x180002451`
- `OLEAUT32!__imp_SysFreeString` at `0x1800024c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800024d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800024c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800024d3`
- `OLEAUT32!__imp_SysStringLen` at `0x1800024a4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800024a4`

## pseudocode

```c
__int64 __fastcall GetPropertyString(struct IAppHostElement *a1, const unsigned __int16 *a2, struct STBUFF *a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  int appended; // ebx
  UINT v8; // eax
  _QWORD v10[3]; // [rsp+20h] [rbp-18h] BYREF
  BSTR pbstr; // [rsp+58h] [rbp+20h] BYREF

  v10[0] = 0;
  pbstr = 0;
  v5 = SysAllocString(a2);
  v6 = v5;
  if ( v5 )
  {
    appended = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, _QWORD *))a1->lpVtbl->GetPropertyByName)(
                 a1,
                 v5,
                 v10);
    if ( appended >= 0 )
    {
      appended = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)v10[0] + 56LL))(v10[0], &pbstr);
      if ( appended >= 0 )
      {
        v8 = SysStringLen(pbstr);
        appended = STBUFF::AppendData(a3, pbstr, 2 * v8, 0);
      }
    }
    SysFreeString(v6);
  }
  else
  {
    appended = -2147024882;
  }
  if ( pbstr )
  {
    SysFreeString(pbstr);
    pbstr = 0;
  }
  if ( v10[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10[0] + 16LL))(v10[0]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180002428  mov     rax, rsp
0x18000242b  mov     [rax+8], rbx
0x18000242f  mov     [rax+10h], rsi
0x180002433  push    rdi
0x180002434  sub     rsp, 30h
0x180002438  mov     rbx, rcx
0x18000243b  mov     qword ptr [rax-18h], 0
0x180002443  mov     rcx, rdx; psz
0x180002446  mov     qword ptr [rax+20h], 0
0x18000244e  mov     rsi, r8
0x180002451  call    cs:__imp_SysAllocString
0x180002457  mov     rdi, rax
0x18000245a  test    rax, rax
0x18000245d  jnz     short loc_180002466
0x18000245f  mov     ebx, 8007000Eh
0x180002464  jmp     short loc_1800024C9
0x180002466  mov     rax, [rbx]
0x180002469  lea     r8, [rsp+38h+var_18]
0x18000246e  mov     rdx, rdi
0x180002471  mov     rcx, rbx
0x180002474  mov     rax, [rax+58h]
0x180002478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000247d  mov     ebx, eax
0x18000247f  test    eax, eax
0x180002481  js      short loc_1800024C0
0x180002483  mov     rcx, [rsp+38h+var_18]
0x180002488  lea     rdx, [rsp+38h+pbstr]
0x18000248d  mov     rax, [rcx]
0x180002490  mov     rax, [rax+38h]
0x180002494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002499  mov     ebx, eax
0x18000249b  test    eax, eax
0x18000249d  js      short loc_1800024C0
0x18000249f  mov     rcx, [rsp+38h+pbstr]; pbstr
0x1800024a4  call    cs:__imp_SysStringLen
0x1800024aa  mov     rdx, [rsp+38h+pbstr]; void *
0x1800024af  xor     r9d, r9d; unsigned int
0x1800024b2  mov     rcx, rsi; this
0x1800024b5  lea     r8d, [rax+rax]; unsigned int
0x1800024b9  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x1800024be  mov     ebx, eax
0x1800024c0  mov     rcx, rdi; bstrString
0x1800024c3  call    cs:__imp_SysFreeString
0x1800024c9  mov     rcx, [rsp+38h+pbstr]; bstrString
0x1800024ce  test    rcx, rcx
0x1800024d1  jz      short loc_1800024E2
0x1800024d3  call    cs:__imp_SysFreeString
0x1800024d9  mov     [rsp+38h+pbstr], 0
0x1800024e2  mov     rcx, [rsp+38h+var_18]
0x1800024e7  test    rcx, rcx
0x1800024ea  jz      short loc_1800024F8
0x1800024ec  mov     rax, [rcx]
0x1800024ef  mov     rax, [rax+10h]
0x1800024f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024f8  mov     rsi, [rsp+38h+arg_8]
0x1800024fd  mov     eax, ebx
0x1800024ff  mov     rbx, [rsp+38h+arg_0]
0x180002504  add     rsp, 30h
0x180002508  pop     rdi
0x180002509  retn
```
