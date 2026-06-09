# CComponentData::_UpdateCurFocusSystemRoot(void)

- ea: `0x180008b70`
- end: `0x180008bd9`
- name: `?_UpdateCurFocusSystemRoot@CComponentData@@AEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CComponentData *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006340`
- `0x180006fc0`
- `0x180008958`

## callees

- `0x180005f64`
- `0x180008b70`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001fcf0`

## pseudocode

```c
void __fastcall CComponentData::_UpdateCurFocusSystemRoot(CComponentData *this)
{
  const WCHAR *CurrentFocus; // rax
  HCURSOR v3; // r8
  HKEY phkResult; // [rsp+38h] [rbp+10h] BYREF

  CurrentFocus = CComponentData::GetCurrentFocus(this);
  if ( CurrentFocus && *CurrentFocus )
  {
    phkResult = 0;
    if ( (int)CSafeReg::Connect(&phkResult, CurrentFocus, v3) >= 0 )
      GetRemoteSystemRoot(phkResult, (unsigned __int16 *)this + 306, 0x105u);
    CSafeReg::Close((CSafeReg *)&phkResult);
  }
  else
  {
    *((_WORD *)this + 306) = 0;
  }
}

```

## disassembly

```asm
0x180008b70  mov     [rsp+arg_0], rbx
0x180008b75  push    rdi
0x180008b76  sub     rsp, 20h
0x180008b7a  mov     rbx, rcx
0x180008b7d  call    ?GetCurrentFocus@CComponentData@@QEAAPEBGXZ; CComponentData::GetCurrentFocus(void)
0x180008b82  xor     edi, edi
0x180008b84  test    rax, rax
0x180008b87  jz      short loc_180008BC7
0x180008b89  cmp     [rax], di
0x180008b8c  jz      short loc_180008BC7
0x180008b8e  mov     rdx, rax; lpMachineName
0x180008b91  mov     [rsp+28h+phkResult], rdi
0x180008b96  lea     rcx, [rsp+28h+phkResult]; phkResult
0x180008b9b  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x180008ba0  test    eax, eax
0x180008ba2  js      short loc_180008BBB
0x180008ba4  mov     rcx, [rsp+28h+phkResult]; HKEY
0x180008ba9  lea     rdx, [rbx+264h]; unsigned __int16 *
0x180008bb0  mov     r8d, 105h; unsigned int
0x180008bb6  call    ?GetRemoteSystemRoot@@YAJPEAUHKEY__@@PEAGK@Z; GetRemoteSystemRoot(HKEY__ *,ushort *,ulong)
0x180008bbb  lea     rcx, [rsp+28h+phkResult]; this
0x180008bc0  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180008bc5  jmp     short loc_180008BCE
0x180008bc7  mov     [rbx+264h], di
0x180008bce  mov     rbx, [rsp+28h+arg_0]
0x180008bd3  add     rsp, 20h
0x180008bd7  pop     rdi
0x180008bd8  retn
```
