# CUstComputer::_ConstructFilterString(ushort * *)

- ea: `0x18001bb38`
- end: `0x18001bc8d`
- name: `?_ConstructFilterString@CUstComputer@@KAJPEAPEAG@Z`
- size: `341`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c284`

## callees

- `0x180003b80`
- `0x180008e5c`
- `0x180008ea0`
- `0x18000baec`
- `0x18001afa0`
- `0x18001bb38`
- `0x18001bd9c`

## string_xrefs

- `0x18001bb84`: `(&(objectClass=Computer)(cn=`
- `0x18001bc3d`: `(&(objectClass=Computer)(cn=`

## pseudocode

```c
__int64 __fastcall CUstComputer::_ConstructFilterString(unsigned __int16 **a1)
{
  unsigned __int64 v2; // rsi
  HRESULT ComputerName; // ebx
  unsigned int v4; // r11d
  unsigned int v5; // r11d
  HRESULT v6; // eax
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  __int64 v10; // r9
  unsigned __int64 v12; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 *v13; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int64 v14; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int64 v15; // [rsp+68h] [rbp+38h] BYREF

  v13 = 0;
  v2 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  ComputerName = CUstComputer::_GetComputerName(&v13);
  if ( ComputerName >= 0 )
  {
    ComputerName = StringCchLengthW(L"(&(objectClass=Computer)(cn=", 0x7FFFFFFFu, &v12);
    if ( ComputerName >= 0 )
    {
      ComputerName = StringCchLengthW(v13, v4, &v15);
      if ( ComputerName >= 0 )
      {
        v6 = StringCchLengthW(L"))", v5, &v14);
        v2 = v14;
        ComputerName = v6;
      }
    }
  }
  if ( ComputerName >= 0 )
  {
    v7 = v2 + v15 + v12 + 1;
    v8 = 2 * v7;
    if ( !is_mul_ok(v7, 2u) )
      v8 = -1;
    v9 = (unsigned __int16 *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    *a1 = v9;
    if ( v9 )
    {
      ComputerName = StringCchCopyW(v9, v7, L"(&(objectClass=Computer)(cn=");
      if ( ComputerName >= 0 )
      {
        ComputerName = StringCchCatW(*a1, v7, v13);
        if ( ComputerName >= 0 )
          return (unsigned int)StringCchCatW(*a1, v7, L"))");
      }
    }
    else
    {
      ComputerName = -2147024882;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v10);
      }
    }
  }
  return (unsigned int)ComputerName;
}

```

## disassembly

```asm
0x18001bb38  mov     [rsp-18h+arg_0], rbx
0x18001bb3d  push    rbp
0x18001bb3e  push    rsi
0x18001bb3f  push    rdi
0x18001bb40  mov     rbp, rsp
0x18001bb43  sub     rsp, 30h
0x18001bb47  mov     rdi, rcx
0x18001bb4a  mov     [rbp+arg_8], 0
0x18001bb52  xor     esi, esi
0x18001bb54  mov     [rbp+var_10], 0
0x18001bb5c  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x18001bb60  mov     [rbp+arg_10], rsi
0x18001bb64  mov     [rbp+arg_18], 0
0x18001bb6c  call    ?_GetComputerName@CUstComputer@@KAJPEAPEAG@Z; CUstComputer::_GetComputerName(ushort * *)
0x18001bb71  mov     ebx, eax
0x18001bb73  test    eax, eax
0x18001bb75  js      short loc_18001BBC5
0x18001bb77  mov     r11d, 7FFFFFFFh
0x18001bb7d  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18001bb81  mov     edx, r11d; unsigned __int64
0x18001bb84  lea     rcx, aObjectclassCom; "(&(objectClass=Computer)(cn="
0x18001bb8b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001bb90  mov     ebx, eax
0x18001bb92  test    eax, eax
0x18001bb94  js      short loc_18001BBC5
0x18001bb96  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x18001bb9a  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18001bb9e  mov     edx, r11d; unsigned __int64
0x18001bba1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001bba6  mov     ebx, eax
0x18001bba8  test    eax, eax
0x18001bbaa  js      short loc_18001BBC5
0x18001bbac  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x18001bbb0  mov     edx, r11d; unsigned __int64
0x18001bbb3  lea     rcx, asc_1800242CC; "))"
0x18001bbba  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001bbbf  mov     rsi, [rbp+arg_10]
0x18001bbc3  mov     ebx, eax
0x18001bbc5  test    ebx, ebx
0x18001bbc7  js      loc_18001BC7E
0x18001bbcd  mov     rcx, [rbp+arg_18]
0x18001bbd1  mov     eax, 2
0x18001bbd6  add     rcx, rsi
0x18001bbd9  mov     rsi, [rbp+var_10]
0x18001bbdd  inc     rsi
0x18001bbe0  add     rsi, rcx
0x18001bbe3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bbea  mul     rsi
0x18001bbed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bbf4  cmovb   rax, rcx
0x18001bbf8  mov     rcx, rax; unsigned __int64
0x18001bbfb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bc00  mov     [rdi], rax
0x18001bc03  test    rax, rax
0x18001bc06  jnz     short loc_18001BC3D
0x18001bc08  mov     ebx, 8007000Eh
0x18001bc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc14  lea     rax, WPP_GLOBAL_Control
0x18001bc1b  cmp     rcx, rax
0x18001bc1e  jz      short loc_18001BC7E
0x18001bc20  test    byte ptr [rcx+1Ch], 1
0x18001bc24  jz      short loc_18001BC7E
0x18001bc26  mov     rcx, [rcx+10h]
0x18001bc2a  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001bc31  mov     edx, 1Ah
0x18001bc36  call    WPP_SF_
0x18001bc3b  jmp     short loc_18001BC7E
0x18001bc3d  lea     r8, aObjectclassCom; "(&(objectClass=Computer)(cn="
0x18001bc44  mov     rdx, rsi; unsigned __int64
0x18001bc47  mov     rcx, rax; unsigned __int16 *
0x18001bc4a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001bc4f  mov     ebx, eax
0x18001bc51  test    eax, eax
0x18001bc53  js      short loc_18001BC7E
0x18001bc55  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x18001bc59  mov     rdx, rsi; unsigned __int64
0x18001bc5c  mov     rcx, [rdi]; unsigned __int16 *
0x18001bc5f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bc64  mov     ebx, eax
0x18001bc66  test    eax, eax
0x18001bc68  js      short loc_18001BC7E
0x18001bc6a  mov     rcx, [rdi]; unsigned __int16 *
0x18001bc6d  lea     r8, asc_1800242CC; "))"
0x18001bc74  mov     rdx, rsi; unsigned __int64
0x18001bc77  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bc7c  mov     ebx, eax
0x18001bc7e  mov     eax, ebx
0x18001bc80  mov     rbx, [rsp+30h+arg_0]
0x18001bc85  add     rsp, 30h
0x18001bc89  pop     rdi
0x18001bc8a  pop     rsi
0x18001bc8b  pop     rbp
0x18001bc8c  retn
```
