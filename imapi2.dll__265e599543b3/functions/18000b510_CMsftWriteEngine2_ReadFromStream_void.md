# CMsftWriteEngine2::ReadFromStream(void)

- ea: `0x18000b510`
- end: `0x18000b7bf`
- name: `?ReadFromStream@CMsftWriteEngine2@@QEAAJXZ`
- size: `687`
- prototype: `__int64 __fastcall(CMsftWriteEngine2 *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800361c8`

## callees

- `0x180002fc8`
- `0x18000b510`
- `0x18000b7c8`
- `0x18000f874`
- `0x1800140f4`
- `0x1800141d8`
- `0x180014250`
- `0x1800236b4`
- `0x18004a010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000b673`
- `KERNEL32!SetEvent` at `0x18000b673`

## pseudocode

```c
__int64 __fastcall CMsftWriteEngine2::ReadFromStream(CMsftWriteEngine2 *this)
{
  __int64 v1; // rbx
  int v3; // edi
  int v4; // r12d
  const struct _GUID *v5; // r8
  __int64 *v6; // r15
  signed int v7; // ebx
  CWriteEngineSectionResources *v8; // rcx
  int v9; // eax
  unsigned __int8 *Buffer; // rax
  __int64 v11; // rcx
  unsigned __int8 *v12; // rbx
  int v13; // r14d
  unsigned int v14; // esi
  __int64 v15; // rax
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+28h] [rbp-50h]
  int v20; // [rsp+30h] [rbp-48h]
  unsigned int v21; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v22; // [rsp+88h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 17);
  v3 = *(_DWORD *)(v1 + 28);
  v4 = *(_DWORD *)(v1 + 36);
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v1 + 48) + 8LL))(*(_QWORD *)(v1 + 48));
  v6 = *(__int64 **)(v1 + 48);
  while ( 1 )
  {
    v7 = 0;
    if ( v4 <= 0 )
      break;
    v8 = (CWriteEngineSectionResources *)*((_QWORD *)this + 16);
    v21 = -2097152;
    v9 = CWriteEngineSectionResources::WaitForNextReadBuffer(v8, &v21);
    v7 = v9;
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          10,
          &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids,
          (unsigned int)v9);
      }
      break;
    }
    Buffer = CWriteEngineSectionResources::get_Buffer(*((CWriteEngineSectionResources **)this + 16), v21);
    v11 = *((_QWORD *)this + 17);
    v12 = Buffer;
    v13 = v4;
    if ( *(_DWORD *)(v11 + 56) <= v4 )
      v13 = *(_DWORD *)(v11 + 56);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 5u )
    {
      v20 = v3;
      v19 = v3;
      v18 = v13;
      WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 27), 11, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids);
    }
    v14 = *(_DWORD *)(*((_QWORD *)this + 17) + 40LL) * v13;
    v15 = *v6;
    v22 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int8 *, _QWORD, unsigned int *, int, int, int))(v15 + 24))(
           v6,
           v12,
           v14,
           &v22,
           v18,
           v19,
           v20);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_dDdDd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          12,
          &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids,
          v14,
          v14,
          v3,
          v3,
          v7);
      }
      break;
    }
    if ( v22 != v14 )
    {
      v7 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_dDdDdD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          13,
          &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids,
          v22,
          v22,
          v14,
          v14,
          v3,
          v3);
      }
      break;
    }
    v3 += v13;
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 18) + 92LL), v14);
    v16 = v21;
    *(_DWORD *)(*((_QWORD *)this + 18) + 72LL) = v3 - 1;
    SetEvent(*(HANDLE *)(*(_QWORD *)(*((_QWORD *)this + 16) + 48LL) + 8 * v16));
    v4 -= v13;
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
  if ( (v7 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v7, (int)&CLSID_MsftWriteEngine2, v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b510  mov     [rsp+arg_10], rbx
0x18000b515  mov     [rsp+arg_18], rbp
0x18000b51a  push    rsi
0x18000b51b  push    rdi
0x18000b51c  push    r12
0x18000b51e  push    r14
0x18000b520  push    r15
0x18000b522  sub     rsp, 50h
0x18000b526  mov     rbx, [rcx+88h]
0x18000b52d  mov     rbp, rcx
0x18000b530  mov     rcx, [rbx+30h]
0x18000b534  mov     edi, [rbx+1Ch]
0x18000b537  mov     r12d, [rbx+24h]
0x18000b53b  mov     rax, [rcx]
0x18000b53e  mov     rax, [rax+8]
0x18000b542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b547  mov     r15, [rbx+30h]
0x18000b54b  xor     ebx, ebx
0x18000b54d  lea     rsi, WPP_GLOBAL_Control
0x18000b554  test    r12d, r12d
0x18000b557  jle     loc_18000B774
0x18000b55d  mov     rcx, [rbp+80h]; this
0x18000b564  lea     rdx, [rsp+78h+arg_0]; unsigned int *
0x18000b56c  mov     [rsp+78h+arg_0], 0FFE00000h
0x18000b577  call    ?WaitForNextReadBuffer@CWriteEngineSectionResources@@QEAAJPEAK@Z; CWriteEngineSectionResources::WaitForNextReadBuffer(ulong *)
0x18000b57c  mov     ebx, eax
0x18000b57e  test    eax, eax
0x18000b580  js      loc_18000B73B
0x18000b586  mov     edx, [rsp+78h+arg_0]; unsigned int
0x18000b58d  mov     rcx, [rbp+80h]; this
0x18000b594  call    ?get_Buffer@CWriteEngineSectionResources@@QEAAPEAEK@Z; CWriteEngineSectionResources::get_Buffer(ulong)
0x18000b599  mov     rcx, [rbp+88h]
0x18000b5a0  mov     rbx, rax
0x18000b5a3  cmp     [rcx+38h], r12d
0x18000b5a7  mov     r14d, r12d
0x18000b5aa  cmovle  r14d, [rcx+38h]
0x18000b5af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5b6  cmp     rcx, rsi
0x18000b5b9  jz      short loc_18000B5F5
0x18000b5bb  test    byte ptr [rcx+0E4h], 4
0x18000b5c2  jz      short loc_18000B5F5
0x18000b5c4  cmp     byte ptr [rcx+0E1h], 5
0x18000b5cb  jb      short loc_18000B5F5
0x18000b5cd  mov     rcx, [rcx+0D8h]
0x18000b5d4  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x18000b5db  mov     [rsp+78h+var_48], edi
0x18000b5df  mov     edx, 0Bh
0x18000b5e4  mov     [rsp+78h+var_50], edi
0x18000b5e8  mov     r9d, r14d
0x18000b5eb  mov     [rsp+78h+var_58], r14d
0x18000b5f0  call    WPP_SF_DDDd
0x18000b5f5  mov     rax, [rbp+88h]
0x18000b5fc  lea     r9, [rsp+78h+arg_8]
0x18000b604  mov     esi, r14d
0x18000b607  mov     rdx, rbx
0x18000b60a  mov     rcx, r15
0x18000b60d  imul    esi, [rax+28h]
0x18000b611  mov     rax, [r15]
0x18000b614  mov     [rsp+78h+arg_8], 0
0x18000b61f  mov     rax, [rax+18h]
0x18000b623  mov     r8d, esi
0x18000b626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b62b  mov     ebx, eax
0x18000b62d  test    eax, eax
0x18000b62f  js      loc_18000B6E9
0x18000b635  mov     r9d, [rsp+78h+arg_8]
0x18000b63d  cmp     r9d, esi
0x18000b640  jnz     short loc_18000B681
0x18000b642  mov     rax, [rbp+90h]
0x18000b649  add     edi, r14d
0x18000b64c  lock add [rax+5Ch], esi
0x18000b650  mov     rax, [rbp+90h]
0x18000b657  lea     ecx, [rdi-1]
0x18000b65a  mov     edx, [rsp+78h+arg_0]
0x18000b661  mov     [rax+48h], ecx
0x18000b664  mov     rax, [rbp+80h]
0x18000b66b  mov     rcx, [rax+30h]
0x18000b66f  mov     rcx, [rcx+rdx*8]; hEvent
0x18000b673  call    cs:__imp_SetEvent
0x18000b679  sub     r12d, r14d
0x18000b67c  jmp     loc_18000B54B
0x18000b681  mov     ebx, 80004005h
0x18000b686  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b68d  lea     rax, WPP_GLOBAL_Control
0x18000b694  cmp     rcx, rax
0x18000b697  jz      loc_18000B774
0x18000b69d  test    byte ptr [rcx+0E4h], 4
0x18000b6a4  jz      loc_18000B774
0x18000b6aa  cmp     byte ptr [rcx+0E1h], 3
0x18000b6b1  jb      loc_18000B774
0x18000b6b7  mov     rcx, [rcx+0D8h]
0x18000b6be  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x18000b6c5  mov     [rsp+78h+var_38], edi
0x18000b6c9  mov     edx, 0Dh
0x18000b6ce  mov     [rsp+78h+var_40], edi
0x18000b6d2  mov     [rsp+78h+var_48], esi
0x18000b6d6  mov     [rsp+78h+var_50], esi
0x18000b6da  mov     [rsp+78h+var_58], r9d
0x18000b6df  call    WPP_SF_dDdDdD
0x18000b6e4  jmp     loc_18000B774
0x18000b6e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6f0  lea     rax, WPP_GLOBAL_Control
0x18000b6f7  cmp     rcx, rax
0x18000b6fa  jz      short loc_18000B774
0x18000b6fc  test    byte ptr [rcx+0E4h], 4
0x18000b703  jz      short loc_18000B774
0x18000b705  cmp     byte ptr [rcx+0E1h], 3
0x18000b70c  jb      short loc_18000B774
0x18000b70e  mov     rcx, [rcx+0D8h]
0x18000b715  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x18000b71c  mov     [rsp+78h+var_40], ebx
0x18000b720  mov     edx, 0Ch
0x18000b725  mov     [rsp+78h+var_48], edi
0x18000b729  mov     r9d, esi
0x18000b72c  mov     [rsp+78h+var_50], edi
0x18000b730  mov     [rsp+78h+var_58], esi
0x18000b734  call    WPP_SF_dDdDd
0x18000b739  jmp     short loc_18000B774
0x18000b73b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b742  cmp     rcx, rsi
0x18000b745  jz      short loc_18000B774
0x18000b747  test    byte ptr [rcx+0E4h], 4
0x18000b74e  jz      short loc_18000B774
0x18000b750  cmp     byte ptr [rcx+0E1h], 3
0x18000b757  jb      short loc_18000B774
0x18000b759  mov     rcx, [rcx+0D8h]
0x18000b760  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x18000b767  mov     edx, 0Ah
0x18000b76c  mov     r9d, eax
0x18000b76f  call    WPP_SF_d
0x18000b774  test    r15, r15
0x18000b777  jz      short loc_18000B788
0x18000b779  mov     rax, [r15]
0x18000b77c  mov     rcx, r15
0x18000b77f  mov     rax, [rax+10h]
0x18000b783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b788  mov     eax, ebx
0x18000b78a  and     eax, 80FF0000h
0x18000b78f  cmp     eax, 80AA0000h
0x18000b794  jnz     short loc_18000B7A4
0x18000b796  lea     rdx, CLSID_MsftWriteEngine2; int
0x18000b79d  mov     ecx, ebx; dwMessageId
0x18000b79f  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18000b7a4  lea     r11, [rsp+78h+var_28]
0x18000b7a9  mov     eax, ebx
0x18000b7ab  mov     rbx, [r11+40h]
0x18000b7af  mov     rbp, [r11+48h]
0x18000b7b3  mov     rsp, r11
0x18000b7b6  pop     r15
0x18000b7b8  pop     r14
0x18000b7ba  pop     r12
0x18000b7bc  pop     rdi
0x18000b7bd  pop     rsi
0x18000b7be  retn
```
