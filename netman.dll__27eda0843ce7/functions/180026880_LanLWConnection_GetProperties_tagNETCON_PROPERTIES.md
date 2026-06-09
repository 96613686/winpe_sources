# LanLWConnection::GetProperties(tagNETCON_PROPERTIES * *)

- ea: `0x180026880`
- end: `0x180026941`
- name: `?GetProperties@LanLWConnection@@UEAAJPEAPEAUtagNETCON_PROPERTIES@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(LanLWConnection *__hidden this, struct tagNETCON_PROPERTIES **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002320`
- `0x18000538c`
- `0x180026570`
- `0x180026880`
- `0x180026b0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026897`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026897`

## pseudocode

```c
__int64 __fastcall LanLWConnection::GetProperties(LanLWConnection *this, struct tagNETCON_PROPERTIES **a2)
{
  unsigned int v2; // edi
  char *v5; // rax
  char *v6; // rbx

  v2 = 0;
  *a2 = 0;
  v5 = (char *)CoTaskMemAlloc(0x50u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x50u);
    *(_OWORD *)v6 = *(_OWORD *)((char *)this + 88);
    LanLWConnection::GetDeviceAliasAndDescr(this, (unsigned __int16 **)v6 + 2, (unsigned __int16 **)v6 + 3);
    LanLWConnection::GetStatus(this, (enum tagNETCON_STATUS *)v6 + 8);
    *((_DWORD *)v6 + 9) = 3;
    *((_DWORD *)v6 + 10) = 1;
    *(_OWORD *)(v6 + 60) = xmmword_18003BB30;
    *(GUID *)(v6 + 44) = CLSID_LanLWConnection;
    *a2 = (struct tagNETCON_PROPERTIES *)v6;
  }
  else
  {
    v2 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_379031154fa533e099be277dc1db0e0f_Traceguids, 2147942414LL);
  }
  return v2;
}

```

## disassembly

```asm
0x180026880  push    rbx
0x180026882  push    rbp
0x180026883  push    rsi
0x180026884  push    rdi
0x180026885  sub     rsp, 28h
0x180026889  xor     edi, edi
0x18002688b  mov     rbp, rcx
0x18002688e  mov     rsi, rdx
0x180026891  mov     [rdx], rdi
0x180026894  lea     ecx, [rdi+50h]; cb
0x180026897  call    cs:__imp_CoTaskMemAlloc
0x18002689d  mov     rbx, rax
0x1800268a0  test    rax, rax
0x1800268a3  jnz     short loc_1800268DB
0x1800268a5  mov     edi, 8007000Eh
0x1800268aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268b1  lea     rax, WPP_GLOBAL_Control
0x1800268b8  cmp     rcx, rax
0x1800268bb  jz      short loc_180026936
0x1800268bd  test    byte ptr [rcx+1Ch], 1
0x1800268c1  jz      short loc_180026936
0x1800268c3  mov     rcx, [rcx+10h]
0x1800268c7  lea     edx, [rbx+11h]
0x1800268ca  mov     r9d, edi
0x1800268cd  lea     r8, WPP_379031154fa533e099be277dc1db0e0f_Traceguids
0x1800268d4  call    WPP_SF_d
0x1800268d9  jmp     short loc_180026936
0x1800268db  xor     edx, edx; Val
0x1800268dd  mov     rcx, rbx; void *
0x1800268e0  lea     r8d, [rdx+50h]; Size
0x1800268e4  call    memset_0
0x1800268e9  movups  xmm0, xmmword ptr [rbp+58h]
0x1800268ed  lea     r8, [rbx+18h]; unsigned __int16 **
0x1800268f1  mov     rcx, rbp; this
0x1800268f4  lea     rdx, [rbx+10h]; unsigned __int16 **
0x1800268f8  movdqu  xmmword ptr [rbx], xmm0
0x1800268fc  call    ?GetDeviceAliasAndDescr@LanLWConnection@@AEAAJPEAPEAG0@Z; LanLWConnection::GetDeviceAliasAndDescr(ushort * *,ushort * *)
0x180026901  lea     rdx, [rbx+20h]; enum tagNETCON_STATUS *
0x180026905  mov     rcx, rbp; this
0x180026908  call    ?GetStatus@LanLWConnection@@QEAAJPEAW4tagNETCON_STATUS@@@Z; LanLWConnection::GetStatus(tagNETCON_STATUS *)
0x18002690d  movups  xmm1, cs:xmmword_18003BB30
0x180026914  mov     dword ptr [rbx+24h], 3
0x18002691b  mov     dword ptr [rbx+28h], 1
0x180026922  movups  xmm0, xmmword ptr cs:CLSID_LanLWConnection.Data1
0x180026929  movdqu  xmmword ptr [rbx+3Ch], xmm1
0x18002692e  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x180026933  mov     [rsi], rbx
0x180026936  mov     eax, edi
0x180026938  add     rsp, 28h
0x18002693c  pop     rdi
0x18002693d  pop     rsi
0x18002693e  pop     rbp
0x18002693f  pop     rbx
0x180026940  retn
```
