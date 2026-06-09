# COSKKeyboardManager::UpdateHostedKeyboardSettings(void)

- ea: `0x140013b1c`
- end: `0x140013cae`
- name: `?UpdateHostedKeyboardSettings@COSKKeyboardManager@@AEAAJXZ`
- size: `402`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140011648`
- `0x140013cb4`

## callees

- `0x14000dd8c`
- `0x140013b1c`
- `0x140019ae8`
- `0x140019c68`
- `0x140025d70`
- `0x140027010`

## pseudocode

```c
__int64 __fastcall COSKKeyboardManager::UpdateHostedKeyboardSettings(COSKKeyboardManager *this)
{
  char *v2; // rbx
  __int64 v3; // rcx
  int v4; // edi
  __int64 v5; // r8
  __int64 v6; // rsi
  COSKHardwareManager *v7; // rcx
  bool v8; // al
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-28h] BYREF

  v2 = (char *)this + 160;
  v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 3) + 232LL))(
         *((_QWORD *)this + 3),
         (char *)this + 160);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 4) + 232LL))(
           *((_QWORD *)this + 4),
           (char *)this + 160);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 5) + 232LL))(
             *((_QWORD *)this + 5),
             (char *)this + 160);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 7) + 232LL))(
               *((_QWORD *)this + 7),
               (char *)this + 160);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 8) + 232LL))(
                 *((_QWORD *)this + 8),
                 (char *)this + 160);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 9) + 232LL))(
                   *((_QWORD *)this + 9),
                   (char *)this + 160);
            if ( v4 >= 0 )
            {
              if ( !*((_QWORD *)this + 29)
                || (v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 232LL))(
                           *((_QWORD *)this + 6),
                           (char *)this + 160),
                    v4 >= 0) )
              {
                v6 = *((_QWORD *)this + 17);
                v7 = *(COSKHardwareManager **)(v6 + 64);
                *(_DWORD *)(v6 + 96) = *((_DWORD *)v2 + 3);
                COSKHardwareManager::ConfigureScanHardware(
                  v7,
                  (struct __MIDL___MIDL_itf_uihosttoskins_0000_0011_0003 *)v2);
                COSKScanManager::SetScanState((COSKScanManager *)v6, 0);
                v8 = *((_DWORD *)v2 + 1) == 3 && *((_DWORD *)v2 + 6);
                *(_BYTE *)(v6 + 150) = v8;
                *(_DWORD *)(v6 + 152) = *((_DWORD *)v2 + 7);
              }
            }
          }
        }
      }
    }
  }
  if ( (Microsoft_Windows_oskEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v3, (const EVENT_DESCRIPTOR *)SwitchMode_Stop, v5, 1u, &v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140013b1c  mov     [rsp+arg_8], rbx
0x140013b21  mov     [rsp+arg_10], rsi
0x140013b26  push    rdi
0x140013b27  sub     rsp, 50h
0x140013b2b  mov     rax, cs:__security_cookie
0x140013b32  xor     rax, rsp
0x140013b35  mov     [rsp+58h+var_18], rax
0x140013b3a  mov     rsi, rcx
0x140013b3d  mov     rcx, [rcx+18h]
0x140013b41  mov     rax, [rcx]
0x140013b44  lea     rbx, [rsi+0A0h]
0x140013b4b  mov     rdx, rbx
0x140013b4e  mov     rax, [rax+0E8h]
0x140013b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b5a  mov     edi, eax
0x140013b5c  test    eax, eax
0x140013b5e  js      loc_140013C6A
0x140013b64  mov     rcx, [rsi+20h]
0x140013b68  mov     rdx, rbx
0x140013b6b  mov     rax, [rcx]
0x140013b6e  mov     rax, [rax+0E8h]
0x140013b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b7a  mov     edi, eax
0x140013b7c  test    eax, eax
0x140013b7e  js      loc_140013C6A
0x140013b84  mov     rcx, [rsi+28h]
0x140013b88  mov     rdx, rbx
0x140013b8b  mov     rax, [rcx]
0x140013b8e  mov     rax, [rax+0E8h]
0x140013b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b9a  mov     edi, eax
0x140013b9c  test    eax, eax
0x140013b9e  js      loc_140013C6A
0x140013ba4  mov     rcx, [rsi+38h]
0x140013ba8  mov     rdx, rbx
0x140013bab  mov     rax, [rcx]
0x140013bae  mov     rax, [rax+0E8h]
0x140013bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013bba  mov     edi, eax
0x140013bbc  test    eax, eax
0x140013bbe  js      loc_140013C6A
0x140013bc4  mov     rcx, [rsi+40h]
0x140013bc8  mov     rdx, rbx
0x140013bcb  mov     rax, [rcx]
0x140013bce  mov     rax, [rax+0E8h]
0x140013bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013bda  mov     edi, eax
0x140013bdc  test    eax, eax
0x140013bde  js      loc_140013C6A
0x140013be4  mov     rcx, [rsi+48h]
0x140013be8  mov     rdx, rbx
0x140013beb  mov     rax, [rcx]
0x140013bee  mov     rax, [rax+0E8h]
0x140013bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013bfa  mov     edi, eax
0x140013bfc  test    eax, eax
0x140013bfe  js      short loc_140013C6A
0x140013c00  cmp     qword ptr [rsi+0E8h], 0
0x140013c08  jz      short loc_140013C26
0x140013c0a  mov     rcx, [rsi+30h]
0x140013c0e  mov     rdx, rbx
0x140013c11  mov     rax, [rcx]
0x140013c14  mov     rax, [rax+0E8h]
0x140013c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c20  mov     edi, eax
0x140013c22  test    eax, eax
0x140013c24  js      short loc_140013C6A
0x140013c26  mov     rsi, [rsi+88h]
0x140013c2d  mov     rdx, rbx; struct __MIDL___MIDL_itf_uihosttoskins_0000_0011_0003 *
0x140013c30  mov     eax, [rbx+0Ch]
0x140013c33  mov     rcx, [rsi+40h]; this
0x140013c37  mov     [rsi+60h], eax
0x140013c3a  call    ?ConfigureScanHardware@COSKHardwareManager@@QEAAXPEAU__MIDL___MIDL_itf_uihosttoskins_0000_0011_0003@@@Z; COSKHardwareManager::ConfigureScanHardware(__MIDL___MIDL_itf_uihosttoskins_0000_0011_0003 *)
0x140013c3f  xor     edx, edx; bool
0x140013c41  mov     rcx, rsi; this
0x140013c44  call    ?SetScanState@COSKScanManager@@AEAAX_N@Z; COSKScanManager::SetScanState(bool)
0x140013c49  cmp     dword ptr [rbx+4], 3
0x140013c4d  jnz     short loc_140013C59
0x140013c4f  cmp     dword ptr [rbx+18h], 0
0x140013c53  jz      short loc_140013C59
0x140013c55  mov     al, 1
0x140013c57  jmp     short loc_140013C5B
0x140013c59  xor     al, al
0x140013c5b  mov     [rsi+96h], al
0x140013c61  mov     eax, [rbx+1Ch]
0x140013c64  mov     [rsi+98h], eax
0x140013c6a  test    cs:Microsoft_Windows_oskEnableBits, 1
0x140013c71  jz      short loc_140013C8F
0x140013c73  lea     rax, [rsp+58h+var_28]
0x140013c78  mov     r9d, 1
0x140013c7e  lea     rdx, SwitchMode_Stop
0x140013c85  mov     [rsp+58h+var_38], rax
0x140013c8a  call    McGenEventWrite_EventWriteTransfer
0x140013c8f  mov     eax, edi
0x140013c91  mov     rcx, [rsp+58h+var_18]
0x140013c96  xor     rcx, rsp; StackCookie
0x140013c99  call    __security_check_cookie
0x140013c9e  mov     rbx, [rsp+58h+arg_8]
0x140013ca3  mov     rsi, [rsp+58h+arg_10]
0x140013ca8  add     rsp, 50h
0x140013cac  pop     rdi
0x140013cad  retn
```
