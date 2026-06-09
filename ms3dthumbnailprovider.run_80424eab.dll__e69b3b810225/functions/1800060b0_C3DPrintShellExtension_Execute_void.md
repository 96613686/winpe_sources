# C3DPrintShellExtension::Execute(void)

- ea: `0x1800060b0`
- end: `0x1800062c9`
- name: `?Execute@C3DPrintShellExtension@@UEAAJXZ`
- size: `537`
- prototype: `__int64 __fastcall(C3DPrintShellExtension *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180001ef0`
- `0x180004dd8`
- `0x180005404`
- `0x1800060b0`
- `0x18000a2dc`
- `0x18000b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800061e7`
- `ole32!CoTaskMemFree` at `0x1800061e7`
- `KERNEL32!CreateThread` at `0x180006243`
- `KERNEL32!CreateThread` at `0x180006243`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x180006217`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x180006217`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall C3DPrintShellExtension::Execute(C3DPrintShellExtension *this)
{
  void *v1; // rdx
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // rbx
  unsigned int (__fastcall *v5)(__int64, __int64, IShellItem **); // rdi
  IShellItem *v6; // rcx
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int128 *v10; // rbx
  void *v11; // rcx
  IShellItem *v12; // rcx
  __int64 v13; // rcx
  IShellItem *psi; // [rsp+30h] [rbp-19h] BYREF
  void *ppv; // [rsp+38h] [rbp-11h] BYREF
  __int64 v17; // [rsp+40h] [rbp-9h] BYREF
  DWORD ThreadId; // [rsp+48h] [rbp-1h] BYREF
  void *Src; // [rsp+50h] [rbp+7h] BYREF
  __int128 v20; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  unsigned __int64 v22; // [rsp+70h] [rbp+27h]

  v1 = 0;
  ppv = 0;
  v2 = *((_QWORD *)this + 4);
  if ( v2 )
  {
    v17 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 72LL))(v2, &v17);
    if ( v3 >= 0 )
    {
      psi = 0;
      v20 = 0;
      v21 = 0;
      v22 = 7;
      LOWORD(v20) = 0;
      Src = 0;
      while ( 1 )
      {
        v4 = v17;
        v5 = *(unsigned int (__fastcall **)(__int64, __int64, IShellItem **))(*(_QWORD *)v17 + 24LL);
        v6 = psi;
        if ( psi )
        {
          psi = 0;
          ((void (__fastcall *)(IShellItem *))v6->lpVtbl->Release)(v6);
        }
        if ( v5(v4, 1, &psi) )
          break;
        if ( !v21 )
        {
          if ( ((int (__fastcall *)(IShellItem *, __int64, void **))psi->lpVtbl->GetDisplayName)(
                 psi,
                 2147844096LL,
                 &Src) >= 0 )
          {
            v7 = -1;
            do
              ++v7;
            while ( *((_WORD *)Src + v7) );
            v8 = v21;
            if ( v7 > v22 - v21 )
            {
              std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
                &v20,
                v7);
            }
            else
            {
              v9 = v7 + v21;
              v21 += v7;
              v10 = &v20;
              if ( v22 > 7 )
                v10 = (__int128 *)v20;
              memmove_0((char *)v10 + 2 * v8, Src, 2 * v7);
              *((_WORD *)v10 + v9) = 0;
            }
            CoTaskMemFree(Src);
          }
          v11 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
          }
          SHCreateShellItemArrayFromShellItem(psi, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &ppv);
        }
      }
      v3 = 0;
      ThreadId = 0;
      CreateThread(0, 0, ProcessFileThread, ppv, 0, &ThreadId);
      ppv = 0;
      std::wstring::~wstring(&v20);
      v12 = psi;
      if ( psi )
      {
        psi = 0;
        ((void (__fastcall *)(IShellItem *))v12->lpVtbl->Release)(v12);
      }
    }
    v13 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v1 = ppv;
  }
  else
  {
    v3 = -2147418113;
  }
  if ( v1 )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v1 + 16LL))(v1);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800060b0  push    rbp
0x1800060b2  push    rbx
0x1800060b3  push    rsi
0x1800060b4  push    rdi
0x1800060b5  lea     rbp, [rsp-3Fh]
0x1800060ba  sub     rsp, 88h
0x1800060c1  mov     rax, cs:__security_cookie
0x1800060c8  xor     rax, rsp
0x1800060cb  mov     [rbp+57h+var_28], rax
0x1800060cf  xor     esi, esi
0x1800060d1  mov     edx, esi
0x1800060d3  mov     [rbp+57h+ppv], rdx
0x1800060d7  mov     rcx, [rcx+20h]
0x1800060db  test    rcx, rcx
0x1800060de  jz      loc_180006291
0x1800060e4  mov     [rbp+57h+var_60], rsi
0x1800060e8  mov     rax, [rcx]
0x1800060eb  lea     rdx, [rbp+57h+var_60]
0x1800060ef  mov     rax, [rax+48h]
0x1800060f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f8  mov     ebx, eax
0x1800060fa  test    eax, eax
0x1800060fc  js      loc_180006271
0x180006102  mov     [rbp+57h+psi], rsi
0x180006106  xorps   xmm0, xmm0
0x180006109  movups  [rbp+57h+var_48], xmm0
0x18000610d  mov     [rbp+57h+var_38], rsi
0x180006111  mov     [rbp+57h+var_30], 7
0x180006119  mov     word ptr [rbp+57h+var_48], si
0x18000611d  mov     [rbp+57h+Src], rsi
0x180006121  mov     rbx, [rbp+57h+var_60]
0x180006125  mov     rax, [rbx]
0x180006128  mov     rdi, [rax+18h]
0x18000612c  mov     rcx, [rbp+57h+psi]
0x180006130  test    rcx, rcx
0x180006133  jz      short loc_180006146
0x180006135  mov     [rbp+57h+psi], rsi
0x180006139  mov     rdx, [rcx]
0x18000613c  mov     rax, [rdx+10h]
0x180006140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006145  nop
0x180006146  xor     r9d, r9d
0x180006149  lea     r8, [rbp+57h+psi]
0x18000614d  lea     edx, [r9+1]
0x180006151  mov     rcx, rbx
0x180006154  mov     rax, rdi
0x180006157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000615c  test    eax, eax
0x18000615e  jnz     loc_180006222
0x180006164  cmp     [rbp+57h+var_38], rsi
0x180006168  jnz     short loc_180006121
0x18000616a  mov     rcx, [rbp+57h+psi]
0x18000616e  mov     rax, [rcx]
0x180006171  lea     r8, [rbp+57h+Src]
0x180006175  mov     edx, 80058000h
0x18000617a  mov     rax, [rax+28h]
0x18000617e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006183  test    eax, eax
0x180006185  js      short loc_1800061EE
0x180006187  mov     r9, [rbp+57h+Src]
0x18000618b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000618f  inc     rdx
0x180006192  cmp     [r9+rdx*2], si
0x180006197  jnz     short loc_18000618F
0x180006199  mov     rcx, [rbp+57h+var_38]
0x18000619d  mov     rax, [rbp+57h+var_30]
0x1800061a1  sub     rax, rcx
0x1800061a4  cmp     rdx, rax
0x1800061a7  ja      short loc_1800061D5
0x1800061a9  lea     rdi, [rdx+rcx]
0x1800061ad  mov     [rbp+57h+var_38], rdi
0x1800061b1  lea     rbx, [rbp+57h+var_48]
0x1800061b5  cmp     [rbp+57h+var_30], 7
0x1800061ba  cmova   rbx, qword ptr [rbp+57h+var_48]
0x1800061bf  lea     r8, [rdx+rdx]; Size
0x1800061c3  lea     rcx, [rbx+rcx*2]; void *
0x1800061c7  mov     rdx, r9; Src
0x1800061ca  call    memmove_0
0x1800061cf  mov     [rbx+rdi*2], si
0x1800061d3  jmp     short loc_1800061E3
0x1800061d5  mov     qword ptr [rsp+0A0h+dwCreationFlags], rdx; __int64
0x1800061da  lea     rcx, [rbp+57h+var_48]; Src
0x1800061de  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x1800061e3  mov     rcx, [rbp+57h+Src]; pv
0x1800061e7  call    cs:__imp_CoTaskMemFree
0x1800061ed  nop
0x1800061ee  mov     rcx, [rbp+57h+ppv]
0x1800061f2  test    rcx, rcx
0x1800061f5  jz      short loc_180006208
0x1800061f7  mov     [rbp+57h+ppv], rsi
0x1800061fb  mov     rax, [rcx]
0x1800061fe  mov     rax, [rax+10h]
0x180006202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006207  nop
0x180006208  lea     r8, [rbp+57h+ppv]; ppv
0x18000620c  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x180006213  mov     rcx, [rbp+57h+psi]; psi
0x180006217  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x18000621d  jmp     loc_180006121
0x180006222  mov     ebx, esi
0x180006224  mov     [rbp+57h+ThreadId], esi
0x180006227  lea     rax, [rbp+57h+ThreadId]
0x18000622b  mov     [rsp+0A0h+lpThreadId], rax; lpThreadId
0x180006230  mov     [rsp+0A0h+dwCreationFlags], esi; dwCreationFlags
0x180006234  mov     r9, [rbp+57h+ppv]; lpParameter
0x180006238  lea     r8, ?ProcessFileThread@@YAKPEAX@Z; lpStartAddress
0x18000623f  xor     edx, edx; dwStackSize
0x180006241  xor     ecx, ecx; lpThreadAttributes
0x180006243  call    cs:__imp_CreateThread
0x180006249  mov     [rbp+57h+ppv], rsi
0x18000624d  lea     rcx, [rbp+57h+var_48]
0x180006251  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006256  nop
0x180006257  mov     rcx, [rbp+57h+psi]
0x18000625b  test    rcx, rcx
0x18000625e  jz      short loc_180006271
0x180006260  mov     [rbp+57h+psi], rsi
0x180006264  mov     rax, [rcx]
0x180006267  mov     rax, [rax+10h]
0x18000626b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006270  nop
0x180006271  mov     rcx, [rbp+57h+var_60]
0x180006275  test    rcx, rcx
0x180006278  jz      short loc_18000628B
0x18000627a  mov     [rbp+57h+var_60], rsi
0x18000627e  mov     rax, [rcx]
0x180006281  mov     rax, [rax+10h]
0x180006285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628a  nop
0x18000628b  mov     rdx, [rbp+57h+ppv]
0x18000628f  jmp     short loc_180006296
0x180006291  mov     ebx, 8000FFFFh
0x180006296  test    rdx, rdx
0x180006299  jz      short loc_1800062AF
0x18000629b  mov     [rbp+57h+ppv], rsi
0x18000629f  mov     rax, [rdx]
0x1800062a2  mov     rcx, rdx
0x1800062a5  mov     rax, [rax+10h]
0x1800062a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ae  nop
0x1800062af  mov     eax, ebx
0x1800062b1  mov     rcx, [rbp+57h+var_28]
0x1800062b5  xor     rcx, rsp; StackCookie
0x1800062b8  call    __security_check_cookie
0x1800062bd  add     rsp, 88h
0x1800062c4  pop     rdi
0x1800062c5  pop     rsi
0x1800062c6  pop     rbx
0x1800062c7  pop     rbp
0x1800062c8  retn
```
