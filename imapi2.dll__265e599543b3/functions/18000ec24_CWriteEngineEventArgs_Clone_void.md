# CWriteEngineEventArgs::Clone(void)

- ea: `0x18000ec24`
- end: `0x18000ed88`
- name: `?Clone@CWriteEngineEventArgs@@QEAAPEAUIDispatch@@XZ`
- size: `356`
- prototype: `struct IDispatch *__fastcall(CWriteEngineEventArgs *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ebd4`

## callees

- `0x18000ec24`
- `0x18000ed90`
- `0x1800140f4`
- `0x180016778`
- `0x18004a010`

## pseudocode

```c
struct IDispatch *__fastcall CWriteEngineEventArgs::Clone(CWriteEngineEventArgs *this)
{
  int v2; // eax
  _DWORD *v3; // rbx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF
  _DWORD *v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v7 = 0;
  v2 = ATL::CComObject<CWriteEngineEventArgs>::CreateInstance(&v8);
  v3 = v8;
  if ( v2 >= 0 )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
    v4 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64 *))v3)(
           v3,
           &GUID_00020400_0000_0000_c000_000000000046,
           &v7);
    if ( v4 >= 0 )
    {
      v3[16] = *((_DWORD *)this + 16);
      v3[17] = *((_DWORD *)this + 17);
      v3[18] = *((_DWORD *)this + 18);
      v3[19] = *((_DWORD *)this + 19);
      v3[20] = *((_DWORD *)this + 20);
      v3[21] = *((_DWORD *)this + 21);
      v3[22] = *((_DWORD *)this + 22);
      v3[23] = *((_DWORD *)this + 23);
      v5 = v7;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        20,
        WPP_6304c543e2b431b01f9b7d5aa18bbdb3_Traceguids,
        (unsigned int)v4);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 19, WPP_6304c543e2b431b01f9b7d5aa18bbdb3_Traceguids);
  }
  v5 = v7;
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v5 = 0;
    v7 = 0;
  }
LABEL_14:
  if ( v3 )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
    return (struct IDispatch *)v7;
  }
  return (struct IDispatch *)v5;
}

```

## disassembly

```asm
0x18000ec24  mov     rax, rsp
0x18000ec27  mov     [rax+8], rbx
0x18000ec2b  push    rdi
0x18000ec2c  sub     rsp, 20h
0x18000ec30  mov     rdi, rcx
0x18000ec33  mov     qword ptr [rax+18h], 0
0x18000ec3b  lea     rcx, [rax+18h]
0x18000ec3f  mov     qword ptr [rax+10h], 0
0x18000ec47  call    ?CreateInstance@?$CComObject@VCWriteEngineEventArgs@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CWriteEngineEventArgs>::CreateInstance(ATL::CComObject<CWriteEngineEventArgs> * *)
0x18000ec4c  mov     rbx, [rsp+28h+arg_10]
0x18000ec51  test    eax, eax
0x18000ec53  jns     short loc_18000ECA0
0x18000ec55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec5c  lea     rax, WPP_GLOBAL_Control
0x18000ec63  cmp     rcx, rax
0x18000ec66  jz      loc_18000ED0D
0x18000ec6c  test    byte ptr [rcx+0E4h], 4
0x18000ec73  jz      loc_18000ED0D
0x18000ec79  cmp     byte ptr [rcx+0E1h], 3
0x18000ec80  jb      loc_18000ED0D
0x18000ec86  mov     rcx, [rcx+0D8h]
0x18000ec8d  lea     r8, WPP_6304c543e2b431b01f9b7d5aa18bbdb3_Traceguids
0x18000ec94  mov     edx, 13h
0x18000ec99  call    WPP_SF_
0x18000ec9e  jmp     short loc_18000ED0D
0x18000eca0  mov     rax, [rbx]
0x18000eca3  mov     rcx, rbx
0x18000eca6  mov     rax, [rax+8]
0x18000ecaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecaf  mov     rax, [rbx]
0x18000ecb2  lea     r8, [rsp+28h+arg_8]
0x18000ecb7  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x18000ecbe  mov     rcx, rbx
0x18000ecc1  mov     rax, [rax]
0x18000ecc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecc9  mov     r9d, eax
0x18000eccc  test    eax, eax
0x18000ecce  jns     short loc_18000ED2C
0x18000ecd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecd7  lea     rax, WPP_GLOBAL_Control
0x18000ecde  cmp     rcx, rax
0x18000ece1  jz      short loc_18000ED0D
0x18000ece3  test    byte ptr [rcx+0E4h], 4
0x18000ecea  jz      short loc_18000ED0D
0x18000ecec  cmp     byte ptr [rcx+0E1h], 2
0x18000ecf3  jb      short loc_18000ED0D
0x18000ecf5  mov     rcx, [rcx+0D8h]
0x18000ecfc  lea     r8, WPP_6304c543e2b431b01f9b7d5aa18bbdb3_Traceguids
0x18000ed03  mov     edx, 14h
0x18000ed08  call    WPP_SF_d
0x18000ed0d  mov     rcx, [rsp+28h+arg_8]
0x18000ed12  test    rcx, rcx
0x18000ed15  jz      short loc_18000ED61
0x18000ed17  mov     rax, [rcx]
0x18000ed1a  mov     rax, [rax+10h]
0x18000ed1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed23  xor     ecx, ecx
0x18000ed25  mov     [rsp+28h+arg_8], rcx
0x18000ed2a  jmp     short loc_18000ED61
0x18000ed2c  mov     eax, [rdi+40h]
0x18000ed2f  mov     [rbx+40h], eax
0x18000ed32  mov     eax, [rdi+44h]
0x18000ed35  mov     [rbx+44h], eax
0x18000ed38  mov     eax, [rdi+48h]
0x18000ed3b  mov     [rbx+48h], eax
0x18000ed3e  mov     eax, [rdi+4Ch]
0x18000ed41  mov     [rbx+4Ch], eax
0x18000ed44  mov     eax, [rdi+50h]
0x18000ed47  mov     [rbx+50h], eax
0x18000ed4a  mov     eax, [rdi+54h]
0x18000ed4d  mov     [rbx+54h], eax
0x18000ed50  mov     eax, [rdi+58h]
0x18000ed53  mov     [rbx+58h], eax
0x18000ed56  mov     eax, [rdi+5Ch]
0x18000ed59  mov     [rbx+5Ch], eax
0x18000ed5c  mov     rcx, [rsp+28h+arg_8]
0x18000ed61  test    rbx, rbx
0x18000ed64  jz      short loc_18000ED7A
0x18000ed66  mov     rax, [rbx]
0x18000ed69  mov     rcx, rbx
0x18000ed6c  mov     rax, [rax+10h]
0x18000ed70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed75  mov     rcx, [rsp+28h+arg_8]
0x18000ed7a  mov     rbx, [rsp+28h+arg_0]
0x18000ed7f  mov     rax, rcx
0x18000ed82  add     rsp, 20h
0x18000ed86  pop     rdi
0x18000ed87  retn
```
