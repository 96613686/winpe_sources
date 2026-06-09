# AnnotateLVCheckBoxForAcc

- ea: `0x18002e7a0`
- end: `0x18002e8ed`
- name: `AnnotateLVCheckBoxForAcc`
- size: `333`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022850`
- `0x18002439c`
- `0x180025878`

## callees

- `0x180001e44`
- `0x18002e7a0`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e7e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e7e9`

## pseudocode

```c
__int64 __fastcall AnnotateLVCheckBoxForAcc(__int64 a1)
{
  unsigned int v2; // edi
  _QWORD *v3; // rbx
  LPVOID v4; // rcx
  LPVOID v6; // [rsp+50h] [rbp-38h] BYREF
  _OWORD v7[2]; // [rsp+58h] [rbp-30h] BYREF

  v6 = 0;
  v2 = CoCreateInstance(&CLSID_AccPropServices, 0, 1u, &IID_IAccPropServices, &v6);
  if ( !v2 && v6 )
  {
    v3 = operator new(0x18u);
    if ( v3 )
    {
      v4 = v6;
      *v3 = &CLVAccPropServer::`vftable';
      v3[2] = 0;
      if ( v4 )
      {
        *((_DWORD *)v3 + 2) = 1;
        v3[2] = v4;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 8LL))(v4);
      }
    }
    else
    {
      v3 = 0;
    }
    if ( v3 )
    {
      v7[0] = PROPID_ACC_STATE;
      v7[1] = PROPID_ACC_ROLE;
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD, _OWORD *, int, _QWORD *, int))(*(_QWORD *)v6 + 64LL))(
             v6,
             a1,
             4294967292LL,
             0,
             v7,
             2,
             v3,
             1);
      (*(void (__fastcall **)(_QWORD *))(*v3 + 16LL))(v3);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v2;
}

```

## disassembly

```asm
0x18002e7a0  mov     r11, rsp
0x18002e7a3  mov     [r11+10h], rbx
0x18002e7a7  mov     [r11+18h], rsi
0x18002e7ab  push    rdi
0x18002e7ac  sub     rsp, 80h
0x18002e7b3  mov     rax, cs:__security_cookie
0x18002e7ba  xor     rax, rsp
0x18002e7bd  mov     [rsp+88h+var_10], rax
0x18002e7c2  xor     edx, edx; pUnkOuter
0x18002e7c4  mov     qword ptr [r11-38h], 0
0x18002e7cc  mov     rsi, rcx
0x18002e7cf  lea     rax, [r11-38h]
0x18002e7d3  lea     r9, IID_IAccPropServices; riid
0x18002e7da  mov     [r11-68h], rax
0x18002e7de  lea     rcx, CLSID_AccPropServices; rclsid
0x18002e7e5  lea     r8d, [rdx+1]; dwClsContext
0x18002e7e9  call    cs:__imp_CoCreateInstance
0x18002e7ef  mov     edi, eax
0x18002e7f1  test    eax, eax
0x18002e7f3  jnz     loc_18002E8C9
0x18002e7f9  cmp     [rsp+88h+var_38], 0
0x18002e7ff  jz      loc_18002E8C9
0x18002e805  lea     ecx, [rax+18h]; Size
0x18002e808  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e80d  mov     rbx, rax
0x18002e810  test    rax, rax
0x18002e813  jz      short loc_18002E84A
0x18002e815  mov     rcx, [rsp+88h+var_38]
0x18002e81a  lea     rax, ??_7CLVAccPropServer@@6B@; const CLVAccPropServer::`vftable'
0x18002e821  mov     [rbx], rax
0x18002e824  mov     qword ptr [rbx+10h], 0
0x18002e82c  test    rcx, rcx
0x18002e82f  jz      short loc_18002E84C
0x18002e831  mov     dword ptr [rbx+8], 1
0x18002e838  mov     [rbx+10h], rcx
0x18002e83c  mov     rax, [rcx]
0x18002e83f  mov     rax, [rax+8]
0x18002e843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e848  jmp     short loc_18002E84C
0x18002e84a  xor     ebx, ebx
0x18002e84c  test    rbx, rbx
0x18002e84f  jz      short loc_18002E8B8
0x18002e851  movups  xmm0, xmmword ptr cs:PROPID_ACC_STATE.Data1
0x18002e858  mov     rcx, [rsp+88h+var_38]
0x18002e85d  lea     rdx, [rsp+88h+var_30]
0x18002e862  movups  xmm1, xmmword ptr cs:PROPID_ACC_ROLE.Data1
0x18002e869  mov     [rsp+88h+var_50], 1
0x18002e871  xor     r9d, r9d
0x18002e874  movdqu  [rsp+88h+var_30], xmm0
0x18002e87a  mov     [rsp+88h+var_58], rbx
0x18002e87f  mov     r8d, 0FFFFFFFCh
0x18002e885  movdqu  [rsp+88h+var_20], xmm1
0x18002e88b  mov     rax, [rcx]
0x18002e88e  mov     [rsp+88h+var_60], 2
0x18002e896  mov     [rsp+88h+var_68], rdx
0x18002e89b  mov     rdx, rsi
0x18002e89e  mov     rax, [rax+40h]
0x18002e8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8a7  mov     edi, eax
0x18002e8a9  mov     rcx, rbx
0x18002e8ac  mov     rax, [rbx]
0x18002e8af  mov     rax, [rax+10h]
0x18002e8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8b8  mov     rcx, [rsp+88h+var_38]
0x18002e8bd  mov     rax, [rcx]
0x18002e8c0  mov     rax, [rax+10h]
0x18002e8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c9  mov     eax, edi
0x18002e8cb  mov     rcx, [rsp+88h+var_10]
0x18002e8d0  xor     rcx, rsp; StackCookie
0x18002e8d3  call    __security_check_cookie
0x18002e8d8  lea     r11, [rsp+88h+var_8]
0x18002e8e0  mov     rbx, [r11+18h]
0x18002e8e4  mov     rsi, [r11+20h]
0x18002e8e8  mov     rsp, r11
0x18002e8eb  pop     rdi
0x18002e8ec  retn
```
