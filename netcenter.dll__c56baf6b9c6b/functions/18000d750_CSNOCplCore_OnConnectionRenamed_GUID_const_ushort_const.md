# CSNOCplCore::OnConnectionRenamed(_GUID const *,ushort const *)

- ea: `0x18000d750`
- end: `0x18000d8a2`
- name: `?OnConnectionRenamed@CSNOCplCore@@UEAAJPEBU_GUID@@PEBG@Z`
- size: `338`
- prototype: `int(CSNOCplCore *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008d70`
- `0x18000d750`
- `0x180010e9c`
- `0x180012324`
- `0x180014274`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d850`
- `USER32!PostMessageW` at `0x18000d824`
- `USER32!PostMessageW` at `0x18000d824`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::OnConnectionRenamed(HWND *this, const struct _GUID *a2, const unsigned __int16 *a3)
{
  int Error; // ebx
  void *v7; // rcx
  LPARAM v8; // rsi
  __int128 v9; // xmm0
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // r9
  void *v13; // rdi
  unsigned __int16 **v15; // [rsp+20h] [rbp-48h]
  unsigned __int64 *v16; // [rsp+28h] [rbp-40h]
  unsigned int v17; // [rsp+30h] [rbp-38h]
  LPARAM lParam; // [rsp+78h] [rbp+10h] BYREF

  Error = -2147467261;
  if ( a2 && a3 )
  {
    lParam = 0;
    Error = CTCoAllocPolicy::Alloc(this, 1u, 0x20u, (void **)&lParam);
    if ( Error >= 0 )
    {
      v8 = lParam;
      *(_QWORD *)lParam = this;
      v9 = (__int128)*a2;
      v10 = -1;
      *(_OWORD *)(v8 + 8) = v9;
      do
        ++v10;
      while ( a3[v10] );
      v11 = v10 + 1;
      if ( v10 + 1 >= v10 && (lParam = 0, is_mul_ok(v11, 2u)) )
      {
        Error = CTCoAllocPolicy::Alloc(v7, (v11 * (unsigned __int128)2uLL) >> 64, 2 * v11, (void **)&lParam);
        if ( Error >= 0 )
        {
          v12 = v10;
          v13 = (void *)lParam;
          StringCchCopyNExW((unsigned __int16 *)lParam, v11, a3, v12, v15, v16, v17);
          *(_QWORD *)(v8 + 24) = v13;
          if ( PostMessageW(this[32], 0x800Du, 0, v8) )
          {
            v13 = 0;
            v8 = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
          CoTaskMemFree(v13);
        }
      }
      else
      {
        Error = -2147024362;
      }
      CoTaskMemFree((LPVOID)v8);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
        (unsigned int)Error);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000d750  mov     rax, rsp
0x18000d753  mov     [rax+8], rbx
0x18000d757  mov     [rax+18h], rbp
0x18000d75b  push    rsi
0x18000d75c  push    rdi
0x18000d75d  push    r12
0x18000d75f  push    r14
0x18000d761  push    r15
0x18000d763  sub     rsp, 40h
0x18000d767  xor     r12d, r12d
0x18000d76a  mov     rbp, r8
0x18000d76d  mov     rdi, rdx
0x18000d770  mov     r15, rcx
0x18000d773  mov     ebx, 80004003h
0x18000d778  test    rdx, rdx
0x18000d77b  jz      loc_18000D887
0x18000d781  test    r8, r8
0x18000d784  jz      loc_18000D887
0x18000d78a  lea     r9, [rax+10h]; void **
0x18000d78e  mov     [rax+10h], r12
0x18000d792  lea     edx, [r12+1]; unsigned int
0x18000d797  lea     r8d, [r12+20h]; unsigned __int64
0x18000d79c  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000d7a1  mov     ebx, eax
0x18000d7a3  test    eax, eax
0x18000d7a5  js      loc_18000D856
0x18000d7ab  mov     rsi, [rsp+68h+lParam]
0x18000d7b0  mov     [rsi], r15
0x18000d7b3  movups  xmm0, xmmword ptr [rdi]
0x18000d7b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000d7ba  movdqu  xmmword ptr [rsi+8], xmm0
0x18000d7bf  inc     rdi
0x18000d7c2  cmp     [rbp+rdi*2+0], r12w
0x18000d7c8  jnz     short loc_18000D7BF
0x18000d7ca  lea     r14, [rdi+1]
0x18000d7ce  cmp     r14, rdi
0x18000d7d1  jb      short loc_18000D848
0x18000d7d3  mov     eax, 2
0x18000d7d8  mov     [rsp+68h+lParam], r12
0x18000d7dd  mul     r14
0x18000d7e0  test    rdx, rdx
0x18000d7e3  jnz     short loc_18000D848
0x18000d7e5  lea     r9, [rsp+68h+lParam]; void **
0x18000d7ea  mov     r8, rax; unsigned __int64
0x18000d7ed  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000d7f2  mov     ebx, eax
0x18000d7f4  test    eax, eax
0x18000d7f6  js      short loc_18000D84D
0x18000d7f8  mov     r9, rdi; unsigned __int64
0x18000d7fb  mov     r8, rbp; unsigned __int16 *
0x18000d7fe  mov     rdi, [rsp+68h+lParam]
0x18000d803  mov     rdx, r14; unsigned __int64
0x18000d806  mov     rcx, rdi; unsigned __int16 *
0x18000d809  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000d80e  mov     [rsi+18h], rdi
0x18000d812  mov     r9, rsi; lParam
0x18000d815  mov     rcx, [r15+100h]; hWnd
0x18000d81c  xor     r8d, r8d; wParam
0x18000d81f  mov     edx, 800Dh; Msg
0x18000d824  call    cs:__imp_PostMessageW
0x18000d82a  test    eax, eax
0x18000d82c  jz      short loc_18000D836
0x18000d82e  mov     rdi, r12
0x18000d831  mov     rsi, r12
0x18000d834  jmp     short loc_18000D83D
0x18000d836  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000d83b  mov     ebx, eax
0x18000d83d  mov     rcx, rdi; pv
0x18000d840  call    cs:__imp_CoTaskMemFree
0x18000d846  jmp     short loc_18000D84D
0x18000d848  mov     ebx, 80070216h
0x18000d84d  mov     rcx, rsi; pv
0x18000d850  call    cs:__imp_CoTaskMemFree
0x18000d856  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d85d  lea     rax, WPP_GLOBAL_Control
0x18000d864  cmp     rcx, rax
0x18000d867  jz      short loc_18000D887
0x18000d869  test    byte ptr [rcx+1Ch], 8
0x18000d86d  jz      short loc_18000D887
0x18000d86f  mov     rcx, [rcx+10h]
0x18000d873  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000d87a  mov     edx, 5Dh ; ']'
0x18000d87f  mov     r9d, ebx
0x18000d882  call    WPP_SF_d
0x18000d887  lea     r11, [rsp+68h+var_28]
0x18000d88c  mov     eax, ebx
0x18000d88e  mov     rbx, [r11+30h]
0x18000d892  mov     rbp, [r11+40h]
0x18000d896  mov     rsp, r11
0x18000d899  pop     r15
0x18000d89b  pop     r14
0x18000d89d  pop     r12
0x18000d89f  pop     rdi
0x18000d8a0  pop     rsi
0x18000d8a1  retn
```
