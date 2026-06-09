# CDX12DecodeCore::CreateNewDecodeDevice(DXVAVideoDesc const &)

- ea: `0x180049810`
- end: `0x1800499b1`
- name: `?CreateNewDecodeDevice@CDX12DecodeCore@@MEAAJAEBUDXVAVideoDesc@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(CDX12DecodeCore *__hidden this, const struct DXVAVideoDesc *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180020598`
- `0x180024220`
- `0x180049810`
- `0x18004e2f8`
- `0x18004e33c`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall CDX12DecodeCore::CreateNewDecodeDevice(CDX12DecodeCore *this, const struct DXVAVideoDesc *a2)
{
  __int64 v2; // rsi
  const struct _GUID *v3; // r12
  __int64 (__fastcall *v6)(__int64, _OWORD *, GUID *, char *); // rdi
  unsigned int v7; // r9d
  int v8; // r10d
  int v9; // r11d
  int v10; // eax
  unsigned int v11; // r10d
  unsigned int v12; // r11d
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, int *, GUID *, char *); // rdi
  _OWORD v16[2]; // [rsp+30h] [rbp-29h] BYREF
  int v17; // [rsp+50h] [rbp-9h] BYREF
  __int128 v18; // [rsp+54h] [rbp-5h]
  __int64 v19; // [rsp+64h] [rbp+Bh]
  int v20; // [rsp+6Ch] [rbp+13h]
  int v21; // [rsp+70h] [rbp+17h]
  int v22; // [rsp+74h] [rbp+1Bh]
  __int64 v23; // [rsp+78h] [rbp+1Fh]
  int v24; // [rsp+80h] [rbp+27h]
  int v25; // [rsp+84h] [rbp+2Bh]

  v2 = *((_QWORD *)this + 3);
  v3 = (const struct _GUID *)((char *)a2 + 12);
  memset(v16, 0, 28);
  *(_OWORD *)((char *)v16 + 4) = *(_OWORD *)((char *)a2 + 12);
  v6 = *(__int64 (__fastcall **)(__int64, _OWORD *, GUID *, char *))(*(_QWORD *)v2 + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 4);
  v7 = v6(v2, v16, &GUID_c59b6bdc_7720_4074_a136_17a156037470, (char *)this + 32);
  if ( v7 )
    return v7;
  v8 = *(_DWORD *)a2;
  v9 = *((_DWORD *)a2 + 1);
  v19 = *(_QWORD *)((char *)&v16[1] + 4);
  v17 = 0;
  v24 = 0;
  v22 = *((_DWORD *)a2 + 2);
  v10 = *((_DWORD *)this + 28);
  v23 = 0;
  v18 = *(_OWORD *)((char *)v16 + 4);
  v20 = v8;
  v21 = v9;
  v25 = v10;
  if ( !_TestMockIsDXVAProfileInBlockList(v3) && v11 <= 0x7FFFFFFF && v12 <= 0x7FFFFFFF )
  {
    if ( _TestMockIsDXVAProfileInEnableList(v3) )
      *((_BYTE *)this + 1385) = 1;
    if ( *((_BYTE *)this + 1385)
      || (v13 = *((_QWORD *)this + 3),
          v14 = *(__int64 (__fastcall **)(__int64, int *, GUID *, char *))(*(_QWORD *)v13 + 40LL),
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 5),
          (v7 = v14(v13, &v17, &GUID_0946b7c9_ebf6_4047_bb73_8683e27dbb1f, (char *)this + 40)) == 0) )
    {
      *(_OWORD *)((char *)this + 1324) = *(_OWORD *)a2;
      *(_OWORD *)((char *)this + 1340) = *((_OWORD *)a2 + 1);
      *(_OWORD *)((char *)this + 1356) = *((_OWORD *)a2 + 2);
      *((_DWORD *)this + 343) = *((_DWORD *)a2 + 12);
    }
    return v7;
  }
  return 2147483661LL;
}

```

## disassembly

```asm
0x180049810  mov     [rsp-8+arg_10], rbx
0x180049815  mov     [rsp-8+arg_18], rsi
0x18004981a  push    rbp
0x18004981b  push    rdi
0x18004981c  push    r12
0x18004981e  push    r14
0x180049820  push    r15
0x180049822  lea     rbp, [rsp-37h]
0x180049827  sub     rsp, 90h
0x18004982e  mov     rax, cs:__security_cookie
0x180049835  xor     rax, rsp
0x180049838  mov     [rbp+57h+var_28], rax
0x18004983c  mov     rsi, [rcx+18h]
0x180049840  lea     r12, [rdx+0Ch]
0x180049844  xorps   xmm0, xmm0
0x180049847  mov     r14, rcx
0x18004984a  movups  [rbp+57h+var_80], xmm0
0x18004984e  add     rcx, 20h ; ' '
0x180049852  mov     r15, rdx
0x180049855  movups  [rbp+57h+var_80+0Ch], xmm0
0x180049859  movups  xmm0, xmmword ptr [r12]
0x18004985e  movdqu  [rbp+57h+var_80+4], xmm0
0x180049863  mov     rax, [rsi]
0x180049866  mov     rdi, [rax+20h]
0x18004986a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004986f  lea     r9, [r14+20h]
0x180049873  mov     rcx, rsi
0x180049876  lea     r8, _GUID_c59b6bdc_7720_4074_a136_17a156037470
0x18004987d  mov     rax, rdi
0x180049880  lea     rdx, [rbp+57h+var_80]
0x180049884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049889  mov     r9d, eax
0x18004988c  test    eax, eax
0x18004988e  jnz     loc_18004997F
0x180049894  mov     ecx, [rbp+57h+var_6C]
0x180049897  movups  xmm0, [rbp+57h+var_80+4]
0x18004989b  mov     r10d, [r15]
0x18004989e  mov     r11d, [r15+4]
0x1800498a2  mov     [rbp+57h+var_4C], ecx
0x1800498a5  mov     ecx, [rbp+57h+var_68]
0x1800498a8  mov     [rbp+57h+var_60], eax
0x1800498ab  mov     [rbp+57h+var_30], eax
0x1800498ae  mov     eax, [r15+8]
0x1800498b2  mov     [rbp+57h+var_48], ecx
0x1800498b5  mov     rcx, r12; struct _GUID *
0x1800498b8  mov     [rbp+57h+var_3C], eax
0x1800498bb  mov     eax, [r14+70h]
0x1800498bf  mov     [rbp+57h+var_38], 0
0x1800498c7  movdqu  [rbp+57h+var_5C], xmm0
0x1800498cc  mov     [rbp+57h+var_44], r10d
0x1800498d0  mov     [rbp+57h+var_40], r11d
0x1800498d4  mov     [rbp+57h+var_2C], eax
0x1800498d7  call    ?_TestMockIsDXVAProfileInBlockList@@YA_NAEBU_GUID@@@Z; _TestMockIsDXVAProfileInBlockList(_GUID const &)
0x1800498dc  test    al, al
0x1800498de  jnz     loc_1800499AA
0x1800498e4  mov     eax, 7FFFFFFFh
0x1800498e9  cmp     r10d, eax
0x1800498ec  ja      loc_1800499AA
0x1800498f2  cmp     r11d, eax
0x1800498f5  ja      loc_1800499AA
0x1800498fb  mov     rcx, r12; struct _GUID *
0x1800498fe  call    ?_TestMockIsDXVAProfileInEnableList@@YA_NAEBU_GUID@@@Z; _TestMockIsDXVAProfileInEnableList(_GUID const &)
0x180049903  test    al, al
0x180049905  jz      short loc_18004990F
0x180049907  mov     byte ptr [r14+569h], 1
0x18004990f  cmp     byte ptr [r14+569h], 0
0x180049917  jnz     short loc_18004994E
0x180049919  mov     rsi, [r14+18h]
0x18004991d  lea     rcx, [r14+28h]
0x180049921  mov     rax, [rsi]
0x180049924  mov     rdi, [rax+28h]
0x180049928  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004992d  lea     r9, [r14+28h]
0x180049931  mov     rcx, rsi
0x180049934  lea     r8, _GUID_0946b7c9_ebf6_4047_bb73_8683e27dbb1f
0x18004993b  mov     rax, rdi
0x18004993e  lea     rdx, [rbp+57h+var_60]
0x180049942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049947  mov     r9d, eax
0x18004994a  test    eax, eax
0x18004994c  jnz     short loc_18004997F
0x18004994e  movups  xmm0, xmmword ptr [r15]
0x180049952  movups  xmmword ptr [r14+52Ch], xmm0
0x18004995a  movups  xmm1, xmmword ptr [r15+10h]
0x18004995f  movups  xmmword ptr [r14+53Ch], xmm1
0x180049967  movups  xmm0, xmmword ptr [r15+20h]
0x18004996c  movups  xmmword ptr [r14+54Ch], xmm0
0x180049974  mov     eax, [r15+30h]
0x180049978  mov     [r14+55Ch], eax
0x18004997f  mov     eax, r9d
0x180049982  mov     rcx, [rbp+57h+var_28]
0x180049986  xor     rcx, rsp; StackCookie
0x180049989  call    __security_check_cookie
0x18004998e  lea     r11, [rsp+0B0h+var_20]
0x180049996  mov     rbx, [r11+40h]
0x18004999a  mov     rsi, [r11+48h]
0x18004999e  mov     rsp, r11
0x1800499a1  pop     r15
0x1800499a3  pop     r14
0x1800499a5  pop     r12
0x1800499a7  pop     rdi
0x1800499a8  pop     rbp
0x1800499a9  retn
0x1800499aa  mov     eax, 8000000Dh
0x1800499af  jmp     short loc_180049982
```
