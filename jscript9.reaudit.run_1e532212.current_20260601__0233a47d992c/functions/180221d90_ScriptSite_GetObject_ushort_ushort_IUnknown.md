# ScriptSite::GetObject(ushort *,ushort *,IUnknown * *)

- ea: `0x180221d90`
- end: `0x180221e8a`
- name: `?GetObject@ScriptSite@@QEAAJPEAG0PEAPEAUIUnknown@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(ScriptSite *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801afdcc`

## callees

- `0x18021d7e8`
- `0x180220f68`
- `0x180221d90`
- `0x180221e90`
- `0x1802226bc`
- `0x180341dd0`
- `0x18035e010`

## import_xrefs

- `OLEAUT32!__imp_GetActiveObject` at `0x180221e27`
- `OLEAUT32!__imp_GetActiveObject` at `0x180221e27`
- `ole32!CLSIDFromProgIDEx` at `0x180221e13`
- `ole32!CLSIDFromProgIDEx` at `0x180221e13`

## pseudocode

```c
int __fastcall ScriptSite::GetObject(
        ScriptSite *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct IUnknown **a4)
{
  int result; // eax
  __int64 v9; // rdx
  int File; // edi
  GUID clsid; // [rsp+20h] [rbp-48h] BYREF

  if ( !a3 )
    return ScriptSite::GetObjectFromMoniker(this, a2, a4);
  if ( a2 )
  {
    result = ScriptSite::CreateObjectFromProgID(this, a3, 0, a4);
    if ( result >= 0 )
    {
      File = ScriptSite::LoadFile(this, *a4, a2);
      if ( File < 0 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
      return File;
    }
  }
  else
  {
    v9 = *((_QWORD *)this + 1);
    clsid = 0;
    if ( (unsigned int)ScriptEngine::IsSafeMode(this, *(_DWORD *)(v9 + 924), 0)
      || *(int *)(*((_QWORD *)this + 20) + 2336LL) >= 3 )
    {
      return -2146827859;
    }
    else
    {
      result = CLSIDFromProgIDEx(a3, &clsid);
      if ( result >= 0 )
        return GetActiveObject(&clsid, 0, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180221d90  mov     r11, rsp
0x180221d93  mov     [r11+20h], r9
0x180221d97  mov     [r11+18h], r8
0x180221d9b  mov     [r11+10h], rdx
0x180221d9f  mov     [r11+8], rcx
0x180221da3  push    rbx
0x180221da4  push    rbp
0x180221da5  push    rsi
0x180221da6  push    rdi
0x180221da7  sub     rsp, 48h
0x180221dab  mov     rax, cs:__security_cookie
0x180221db2  xor     rax, rsp
0x180221db5  mov     [rsp+68h+var_38], rax
0x180221dba  mov     rdi, rcx
0x180221dbd  mov     rsi, rdx
0x180221dc0  mov     rbp, r8
0x180221dc3  mov     rbx, r9
0x180221dc6  test    r8, r8
0x180221dc9  jnz     short loc_180221DD8
0x180221dcb  mov     r8, rbx; struct IUnknown **
0x180221dce  call    ?GetObjectFromMoniker@ScriptSite@@QEAAJPEAGPEAPEAUIUnknown@@@Z; ScriptSite::GetObjectFromMoniker(ushort *,IUnknown * *)
0x180221dd3  jmp     loc_180221E74
0x180221dd8  xor     r8d, r8d; unsigned __int16 *
0x180221ddb  test    rsi, rsi
0x180221dde  jnz     short loc_180221E36
0x180221de0  mov     rdx, [rdi+8]
0x180221de4  xorps   xmm0, xmm0
0x180221de7  movups  xmmword ptr [rsp+68h+clsid.Data1], xmm0
0x180221dec  mov     edx, [rdx+39Ch]; unsigned int
0x180221df2  call    ?IsSafeMode@ScriptEngine@@QEAAHKPEBU_GUID@@@Z; ScriptEngine::IsSafeMode(ulong,_GUID const *)
0x180221df7  test    eax, eax
0x180221df9  jnz     short loc_180221E2F
0x180221dfb  mov     rax, [rdi+0A0h]
0x180221e02  cmp     dword ptr [rax+920h], 3
0x180221e09  jge     short loc_180221E2F
0x180221e0b  lea     rdx, [rsp+68h+clsid]; lpclsid
0x180221e10  mov     rcx, rbp; lpszProgID
0x180221e13  call    cs:__imp_CLSIDFromProgIDEx
0x180221e19  test    eax, eax
0x180221e1b  js      short loc_180221E74
0x180221e1d  mov     r8, rbx; ppunk
0x180221e20  lea     rcx, [rsp+68h+clsid]; rclsid
0x180221e25  xor     edx, edx; pvReserved
0x180221e27  call    cs:__imp_GetActiveObject
0x180221e2d  jmp     short loc_180221E74
0x180221e2f  mov     eax, 800A01ADh
0x180221e34  jmp     short loc_180221E74
0x180221e36  mov     r9, rbx; struct IUnknown **
0x180221e39  mov     rdx, rbp; unsigned __int16 *
0x180221e3c  mov     rcx, rdi; this
0x180221e3f  call    ?CreateObjectFromProgID@ScriptSite@@QEAAJPEBG0PEAPEAUIUnknown@@@Z; ScriptSite::CreateObjectFromProgID(ushort const *,ushort const *,IUnknown * *)
0x180221e44  test    eax, eax
0x180221e46  js      short loc_180221E74
0x180221e48  mov     rdx, [rbx]; struct IUnknown *
0x180221e4b  mov     r8, rsi; unsigned __int16 *
0x180221e4e  mov     rcx, rdi; this
0x180221e51  call    ?LoadFile@ScriptSite@@QEAAJPEAUIUnknown@@PEAG@Z; ScriptSite::LoadFile(IUnknown *,ushort *)
0x180221e56  mov     edi, eax
0x180221e58  test    eax, eax
0x180221e5a  jns     short loc_180221E72
0x180221e5c  mov     rcx, [rbx]
0x180221e5f  mov     rdx, [rcx]
0x180221e62  mov     rax, [rdx+10h]
0x180221e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221e6b  mov     qword ptr [rbx], 0
0x180221e72  mov     eax, edi
0x180221e74  mov     rcx, [rsp+68h+var_38]
0x180221e79  xor     rcx, rsp; StackCookie
0x180221e7c  call    __security_check_cookie
0x180221e81  add     rsp, 48h
0x180221e85  pop     rdi
0x180221e86  pop     rsi
0x180221e87  pop     rbp
0x180221e88  pop     rbx
0x180221e89  retn
```
