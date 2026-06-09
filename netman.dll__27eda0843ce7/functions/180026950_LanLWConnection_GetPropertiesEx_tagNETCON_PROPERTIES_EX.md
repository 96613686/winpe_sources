# LanLWConnection::GetPropertiesEx(tagNETCON_PROPERTIES_EX * *)

- ea: `0x180026950`
- end: `0x180026aaa`
- name: `?GetPropertiesEx@LanLWConnection@@UEAAJPEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(LanLWConnection *__hidden this, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002320`
- `0x18000538c`
- `0x180026570`
- `0x180026950`
- `0x180026b0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026a2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026a4c`
- `OLEAUT32!__imp_SysAllocString` at `0x180026a1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026a3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026a1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180026a3f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180026a88`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180026a88`

## pseudocode

```c
__int64 __fastcall LanLWConnection::GetPropertiesEx(LanLWConnection *this, struct tagNETCON_PROPERTIES_EX **a2)
{
  char *v4; // rax
  char *v5; // rdi
  unsigned int v6; // esi
  OLECHAR *v7; // rbx
  OLECHAR *v8; // rbx
  OLECHAR *psz; // [rsp+48h] [rbp+10h] BYREF
  OLECHAR *v11; // [rsp+50h] [rbp+18h] BYREF

  psz = 0;
  v11 = 0;
  *a2 = 0;
  v4 = (char *)CoTaskMemAlloc(0x68u);
  v5 = v4;
  if ( v4 )
  {
    v6 = 0;
    memset_0(v4 + 4, 0, 0x64u);
    *(_DWORD *)v5 = 104;
    *(_OWORD *)(v5 + 4) = *((_OWORD *)this + 4);
    LanLWConnection::GetDeviceAliasAndDescr((LanLWConnection *)((char *)this - 24), &psz, &v11);
    LanLWConnection::GetStatus((LanLWConnection *)((char *)this - 24), (enum tagNETCON_STATUS *)v5 + 10);
    v7 = psz;
    if ( psz )
    {
      *((_QWORD *)v5 + 3) = SysAllocString(psz);
      CoTaskMemFree(v7);
    }
    v8 = v11;
    if ( v11 )
    {
      *((_QWORD *)v5 + 4) = SysAllocString(v11);
      CoTaskMemFree(v8);
    }
    *((_DWORD *)v5 + 11) = 3;
    *((_DWORD *)v5 + 12) = 1;
    *((_DWORD *)v5 + 13) = 1;
    *(_OWORD *)(v5 + 72) = xmmword_18003BB30;
    *(GUID *)(v5 + 56) = CLSID_LanLWConnection;
    *((_QWORD *)v5 + 12) = SysAllocStringByteLen((LPCSTR)this + 64, 0x10u);
    *a2 = (struct tagNETCON_PROPERTIES_EX *)v5;
  }
  else
  {
    v6 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_379031154fa533e099be277dc1db0e0f_Traceguids, 2147942414LL);
  }
  return v6;
}

```

## disassembly

```asm
0x180026950  mov     rax, rsp
0x180026953  mov     [rax+8], rbx
0x180026957  mov     [rax+20h], rbp
0x18002695b  push    rsi
0x18002695c  push    rdi
0x18002695d  push    r14
0x18002695f  sub     rsp, 20h
0x180026963  mov     rbp, rcx
0x180026966  mov     qword ptr [rax+10h], 0
0x18002696e  mov     ebx, 68h ; 'h'
0x180026973  mov     qword ptr [rax+18h], 0
0x18002697b  mov     ecx, ebx; cb
0x18002697d  mov     qword ptr [rdx], 0
0x180026984  mov     r14, rdx
0x180026987  call    cs:__imp_CoTaskMemAlloc
0x18002698d  mov     rdi, rax
0x180026990  test    rax, rax
0x180026993  jnz     short loc_1800269D6
0x180026995  mov     esi, 8007000Eh
0x18002699a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269a1  lea     rax, WPP_GLOBAL_Control
0x1800269a8  cmp     rcx, rax
0x1800269ab  jz      loc_180026A95
0x1800269b1  test    byte ptr [rcx+1Ch], 1
0x1800269b5  jz      loc_180026A95
0x1800269bb  mov     rcx, [rcx+10h]
0x1800269bf  lea     edx, [rbx-4Fh]
0x1800269c2  mov     r9d, esi
0x1800269c5  lea     r8, WPP_379031154fa533e099be277dc1db0e0f_Traceguids
0x1800269cc  call    WPP_SF_d
0x1800269d1  jmp     loc_180026A95
0x1800269d6  xor     esi, esi
0x1800269d8  lea     rcx, [rax+4]; void *
0x1800269dc  xor     edx, edx; Val
0x1800269de  lea     r8d, [rsi+64h]; Size
0x1800269e2  call    memset_0
0x1800269e7  mov     [rdi], ebx
0x1800269e9  lea     r8, [rsp+38h+arg_10]; unsigned __int16 **
0x1800269ee  movups  xmm0, xmmword ptr [rbp+40h]
0x1800269f2  lea     rdx, [rsp+38h+psz]; unsigned __int16 **
0x1800269f7  lea     rcx, [rbp-18h]; this
0x1800269fb  movdqu  xmmword ptr [rdi+4], xmm0
0x180026a00  call    ?GetDeviceAliasAndDescr@LanLWConnection@@AEAAJPEAPEAG0@Z; LanLWConnection::GetDeviceAliasAndDescr(ushort * *,ushort * *)
0x180026a05  lea     rdx, [rdi+28h]; enum tagNETCON_STATUS *
0x180026a09  lea     rcx, [rbp-18h]; this
0x180026a0d  call    ?GetStatus@LanLWConnection@@QEAAJPEAW4tagNETCON_STATUS@@@Z; LanLWConnection::GetStatus(tagNETCON_STATUS *)
0x180026a12  mov     rbx, [rsp+38h+psz]
0x180026a17  test    rbx, rbx
0x180026a1a  jz      short loc_180026A32
0x180026a1c  mov     rcx, rbx; psz
0x180026a1f  call    cs:__imp_SysAllocString
0x180026a25  mov     rcx, rbx; pv
0x180026a28  mov     [rdi+18h], rax
0x180026a2c  call    cs:__imp_CoTaskMemFree
0x180026a32  mov     rbx, [rsp+38h+arg_10]
0x180026a37  test    rbx, rbx
0x180026a3a  jz      short loc_180026A52
0x180026a3c  mov     rcx, rbx; psz
0x180026a3f  call    cs:__imp_SysAllocString
0x180026a45  mov     rcx, rbx; pv
0x180026a48  mov     [rdi+20h], rax
0x180026a4c  call    cs:__imp_CoTaskMemFree
0x180026a52  movups  xmm1, cs:xmmword_18003BB30
0x180026a59  mov     dword ptr [rdi+2Ch], 3
0x180026a60  lea     rcx, [rbp+40h]; psz
0x180026a64  mov     dword ptr [rdi+30h], 1
0x180026a6b  mov     edx, 10h; len
0x180026a70  mov     dword ptr [rdi+34h], 1
0x180026a77  movups  xmm0, xmmword ptr cs:CLSID_LanLWConnection.Data1
0x180026a7e  movdqu  xmmword ptr [rdi+48h], xmm1
0x180026a83  movdqu  xmmword ptr [rdi+38h], xmm0
0x180026a88  call    cs:__imp_SysAllocStringByteLen
0x180026a8e  mov     [rdi+60h], rax
0x180026a92  mov     [r14], rdi
0x180026a95  mov     rbx, [rsp+38h+arg_0]
0x180026a9a  mov     eax, esi
0x180026a9c  mov     rbp, [rsp+38h+arg_18]
0x180026aa1  add     rsp, 20h
0x180026aa5  pop     r14
0x180026aa7  pop     rdi
0x180026aa8  pop     rsi
0x180026aa9  retn
```
