# CGhostProcess::CreateSiblingFrostWindow(HWND__ *)

- ea: `0x180008eec`
- end: `0x180008fad`
- name: `?CreateSiblingFrostWindow@CGhostProcess@@AEAAHPEAUHWND__@@@Z`
- size: `193`
- prototype: `int(CGhostProcess *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009e90`

## callees

- `0x180001962`
- `0x180004dc4`
- `0x180005bf4`
- `0x180007e34`
- `0x180007e64`
- `0x180008eec`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180008f3f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180008f3f`

## pseudocode

```c
__int64 __fastcall CGhostProcess::CreateSiblingFrostWindow(CGhostProcess *this, HWND a2)
{
  unsigned int v4; // edi
  CGhostMgr *Instance; // rbx
  _BYTE v7[52]; // [rsp+20h] [rbp-29h] BYREF
  int v8; // [rsp+54h] [rbp+Bh]
  HWND v9; // [rsp+58h] [rbp+Fh]
  DWORD v10; // [rsp+60h] [rbp+17h]
  DWORD WindowThreadProcessId; // [rsp+64h] [rbp+1Bh]
  DWORD dwProcessId; // [rsp+C0h] [rbp+77h] BYREF
  CCountedObject *v13; // [rsp+C8h] [rbp+7Fh] BYREF

  v4 = 0;
  Instance = CGhostMgr::GetInstance();
  if ( Instance )
  {
    memset_0(v7, 0, 0x68u);
    dwProcessId = 0;
    v8 = 3;
    v9 = a2;
    WindowThreadProcessId = GetWindowThreadProcessId(a2, &dwProcessId);
    v10 = dwProcessId;
    if ( WindowThreadProcessId )
    {
      if ( dwProcessId == *((_DWORD *)this + 14) )
      {
        v13 = 0;
        if ( (unsigned int)CGhostMgr::HandleRequest(Instance, (struct GHOSTLPCMSG *)v7, &v13) )
        {
          LOBYTE(v4) = CDynamicCountedObjectArray::Add((CGhostProcess *)((char *)this + 72), v13) != 0;
          CCountedObject::Release(v13);
        }
      }
    }
    CCountedObject::Release(Instance);
  }
  return v4;
}

```

## disassembly

```asm
0x180008eec  mov     [rsp-8+arg_0], rbx
0x180008ef1  mov     [rsp-8+arg_8], rsi
0x180008ef6  push    rbp
0x180008ef7  push    rdi
0x180008ef8  push    r14
0x180008efa  lea     rbp, [rsp-47h]
0x180008eff  sub     rsp, 90h
0x180008f06  mov     r14, rdx
0x180008f09  mov     rsi, rcx
0x180008f0c  xor     edi, edi
0x180008f0e  call    ?GetInstance@CGhostMgr@@SAPEAV1@XZ; CGhostMgr::GetInstance(void)
0x180008f13  mov     rbx, rax
0x180008f16  test    rax, rax
0x180008f19  jz      short loc_180008F93
0x180008f1b  xor     edx, edx; Val
0x180008f1d  lea     r8d, [rdi+68h]; Size
0x180008f21  lea     rcx, [rbp+57h+var_80]; void *
0x180008f25  call    memset_0
0x180008f2a  lea     rdx, [rbp+57h+dwProcessId]; lpdwProcessId
0x180008f2e  mov     [rbp+57h+dwProcessId], edi
0x180008f31  mov     rcx, r14; hWnd
0x180008f34  mov     [rbp+57h+var_4C], 3
0x180008f3b  mov     [rbp+57h+var_48], r14
0x180008f3f  call    cs:__imp_GetWindowThreadProcessId
0x180008f45  mov     ecx, [rbp+57h+dwProcessId]
0x180008f48  mov     [rbp+57h+var_3C], eax
0x180008f4b  mov     [rbp+57h+var_40], ecx
0x180008f4e  test    eax, eax
0x180008f50  jz      short loc_180008F8B
0x180008f52  cmp     ecx, [rsi+38h]
0x180008f55  jnz     short loc_180008F8B
0x180008f57  lea     r8, [rbp+57h+arg_18]; struct CGhostWindow **
0x180008f5b  mov     [rbp+57h+arg_18], rdi
0x180008f5f  lea     rdx, [rbp+57h+var_80]; struct GHOSTLPCMSG *
0x180008f63  mov     rcx, rbx; this
0x180008f66  call    ?HandleRequest@CGhostMgr@@QEAAHPEAUGHOSTLPCMSG@@PEAPEAVCGhostWindow@@@Z; CGhostMgr::HandleRequest(GHOSTLPCMSG *,CGhostWindow * *)
0x180008f6b  test    eax, eax
0x180008f6d  jz      short loc_180008F8B
0x180008f6f  mov     rdx, [rbp+57h+arg_18]; struct CCountedObject *
0x180008f73  lea     rcx, [rsi+48h]; this
0x180008f77  call    ?Add@CDynamicCountedObjectArray@@QEAAHPEAVCCountedObject@@@Z; CDynamicCountedObjectArray::Add(CCountedObject *)
0x180008f7c  mov     rcx, [rbp+57h+arg_18]; this
0x180008f80  test    eax, eax
0x180008f82  setnz   dil
0x180008f86  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180008f8b  mov     rcx, rbx; this
0x180008f8e  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180008f93  lea     r11, [rsp+0A0h+var_10]
0x180008f9b  mov     eax, edi
0x180008f9d  mov     rbx, [r11+20h]
0x180008fa1  mov     rsi, [r11+28h]
0x180008fa5  mov     rsp, r11
0x180008fa8  pop     r14
0x180008faa  pop     rdi
0x180008fab  pop     rbp
0x180008fac  retn
```
