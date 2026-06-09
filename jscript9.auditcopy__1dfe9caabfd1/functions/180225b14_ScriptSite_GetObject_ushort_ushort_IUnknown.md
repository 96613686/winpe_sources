# ScriptSite::GetObject(ushort *,ushort *,IUnknown * *)

- ea: `0x180225b14`
- end: `0x180225c1b`
- name: `?GetObject@ScriptSite@@QEAAJPEAG0PEAPEAUIUnknown@@@Z`
- size: `263`
- prototype: `int __fastcall(ScriptSite *this, unsigned __int16 *, unsigned __int16 *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801b27b8`

## callees

- `0x180221514`
- `0x180224e10`
- `0x180225b14`
- `0x180225c24`
- `0x180226468`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `OLEAUT32!__imp_GetActiveObject` at `0x180225bb1`
- `OLEAUT32!__imp_GetActiveObject` at `0x180225bb1`
- `ole32!CLSIDFromProgIDEx` at `0x180225b97`
- `ole32!CLSIDFromProgIDEx` at `0x180225b97`

## pseudocode

```c
int __fastcall ScriptSite::GetObject(ScriptSite *this, unsigned __int16 *a2, unsigned __int16 *a3, LPVOID *a4)
{
  int result; // eax
  __int64 v9; // rdx
  int File; // edi
  GUID clsid; // [rsp+20h] [rbp-48h] BYREF

  if ( !a3 )
    return ScriptSite::GetObjectFromMoniker(this, a2, a4);
  if ( a2 )
  {
    result = ScriptSite::CreateObjectFromProgID(this, a3, 0, (struct IUnknown **)a4);
    if ( result >= 0 )
    {
      File = ScriptSite::LoadFile((ScriptEngine **)this, (struct IUnknown *)*a4, a2);
      if ( File < 0 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*a4 + 16LL))(*a4);
        *a4 = 0;
      }
      return File;
    }
  }
  else
  {
    v9 = *((_QWORD *)this + 1);
    clsid = 0;
    if ( ScriptEngine::IsSafeMode(this, *(_DWORD *)(v9 + 924), 0) || *(int *)(*((_QWORD *)this + 20) + 2336LL) >= 3 )
    {
      return -2146827859;
    }
    else
    {
      result = CLSIDFromProgIDEx(a3, &clsid);
      if ( result >= 0 )
        return GetActiveObject(&clsid, 0, (IUnknown **)a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180225b14  mov     r11, rsp
0x180225b17  mov     [r11+20h], r9
0x180225b1b  mov     [r11+18h], r8
0x180225b1f  mov     [r11+10h], rdx
0x180225b23  mov     [r11+8], rcx
0x180225b27  push    rbx
0x180225b28  push    rbp
0x180225b29  push    rsi
0x180225b2a  push    rdi
0x180225b2b  sub     rsp, 48h
0x180225b2f  mov     rax, cs:__security_cookie
0x180225b36  xor     rax, rsp
0x180225b39  mov     [rsp+68h+var_38], rax
0x180225b3e  mov     rdi, rcx
0x180225b41  mov     rsi, rdx
0x180225b44  mov     rbp, r8
0x180225b47  mov     rbx, r9
0x180225b4a  test    r8, r8
0x180225b4d  jnz     short loc_180225B5C
0x180225b4f  mov     r8, rbx; struct IUnknown **
0x180225b52  call    ?GetObjectFromMoniker@ScriptSite@@QEAAJPEAGPEAPEAUIUnknown@@@Z; ScriptSite::GetObjectFromMoniker(ushort *,IUnknown * *)
0x180225b57  jmp     loc_180225C04
0x180225b5c  xor     r8d, r8d; unsigned __int16 *
0x180225b5f  test    rsi, rsi
0x180225b62  jnz     short loc_180225BC6
0x180225b64  mov     rdx, [rdi+8]
0x180225b68  xorps   xmm0, xmm0
0x180225b6b  movups  xmmword ptr [rsp+68h+clsid.Data1], xmm0
0x180225b70  mov     edx, [rdx+39Ch]; unsigned int
0x180225b76  call    ?IsSafeMode@ScriptEngine@@QEAAHKPEBU_GUID@@@Z; ScriptEngine::IsSafeMode(ulong,_GUID const *)
0x180225b7b  test    eax, eax
0x180225b7d  jnz     short loc_180225BBF
0x180225b7f  mov     rax, [rdi+0A0h]
0x180225b86  cmp     dword ptr [rax+920h], 3
0x180225b8d  jge     short loc_180225BBF
0x180225b8f  lea     rdx, [rsp+68h+clsid]; lpclsid
0x180225b94  mov     rcx, rbp; lpszProgID
0x180225b97  call    cs:__imp_CLSIDFromProgIDEx
0x180225b9e  nop     dword ptr [rax+rax+00h]
0x180225ba3  test    eax, eax
0x180225ba5  js      short loc_180225C04
0x180225ba7  mov     r8, rbx; ppunk
0x180225baa  lea     rcx, [rsp+68h+clsid]; rclsid
0x180225baf  xor     edx, edx; pvReserved
0x180225bb1  call    cs:__imp_GetActiveObject
0x180225bb8  nop     dword ptr [rax+rax+00h]
0x180225bbd  jmp     short loc_180225C04
0x180225bbf  mov     eax, 800A01ADh
0x180225bc4  jmp     short loc_180225C04
0x180225bc6  mov     r9, rbx; struct IUnknown **
0x180225bc9  mov     rdx, rbp; unsigned __int16 *
0x180225bcc  mov     rcx, rdi; this
0x180225bcf  call    ?CreateObjectFromProgID@ScriptSite@@QEAAJPEBG0PEAPEAUIUnknown@@@Z; ScriptSite::CreateObjectFromProgID(ushort const *,ushort const *,IUnknown * *)
0x180225bd4  test    eax, eax
0x180225bd6  js      short loc_180225C04
0x180225bd8  mov     rdx, [rbx]; struct IUnknown *
0x180225bdb  mov     r8, rsi; unsigned __int16 *
0x180225bde  mov     rcx, rdi; this
0x180225be1  call    ?LoadFile@ScriptSite@@QEAAJPEAUIUnknown@@PEAG@Z; ScriptSite::LoadFile(IUnknown *,ushort *)
0x180225be6  mov     edi, eax
0x180225be8  test    eax, eax
0x180225bea  jns     short loc_180225C02
0x180225bec  mov     rcx, [rbx]
0x180225bef  mov     rdx, [rcx]
0x180225bf2  mov     rax, [rdx+10h]
0x180225bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180225bfb  mov     qword ptr [rbx], 0
0x180225c02  mov     eax, edi
0x180225c04  mov     rcx, [rsp+68h+var_38]
0x180225c09  xor     rcx, rsp; StackCookie
0x180225c0c  call    __security_check_cookie
0x180225c11  add     rsp, 48h
0x180225c15  pop     rdi
0x180225c16  pop     rsi
0x180225c17  pop     rbp
0x180225c18  pop     rbx
0x180225c19  retn
```
