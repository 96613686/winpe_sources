# web::json::details::JSON_Parser<ushort>::_ParseValue(web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x14000a3c0`
- end: `0x14000a7a8`
- name: `?_ParseValue@?$JSON_Parser@G@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `1000`
- prototype: `char **__fastcall(web::json::details *, char **, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140008af0`
- `0x140009cb0`
- `0x140009f80`

## callees

- `0x140002f84`
- `0x140007f60`
- `0x1400098a0`
- `0x140009db0`
- `0x140009f80`
- `0x14000a3c0`
- `0x14003e010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char **__fastcall web::json::details::JSON_Parser<unsigned short>::_ParseValue(
        web::json::details *a1,
        char **a2,
        __int64 a3)
{
  __int64 *v6; // rax
  char *v7; // rcx
  char *v8; // rcx
  __int64 v9; // rax
  char *v10; // rbx
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  char v13; // al
  char *v14; // rax
  char *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  char *v19; // rax
  char *v20; // rax
  __int64 v21; // xmm0_8
  char *v22; // rax
  char v23; // al
  char *v24; // rax
  const struct web::json::details::json_error_category_impl *v25; // rax
  char *v26; // rax
  int v27; // [rsp+2Ch] [rbp-5Ch]
  char *v28; // [rsp+A0h] [rbp+18h] BYREF

  switch ( *(_DWORD *)a3 )
  {
    case 1:
      v6 = web::json::details::JSON_Parser<unsigned short>::_ParseObject((__int64)a1, &v28, (unsigned int *)a3);
      goto LABEL_3;
    case 3:
      v6 = web::json::details::JSON_Parser<unsigned short>::_ParseArray((__int64)a1, &v28, a3);
LABEL_3:
      v7 = (char *)*v6;
      *v6 = 0;
      *a2 = v7;
      v8 = v28;
      if ( !v28 )
        return a2;
      v9 = *(_QWORD *)v28;
      goto LABEL_47;
    case 7:
      v10 = (char *)operator new(0x30u);
      v28 = v10;
      if ( v10 )
      {
        v11 = *(_OWORD *)(a3 + 8);
        v12 = *(_OWORD *)(a3 + 24);
        *(_QWORD *)(a3 + 24) = 0;
        *(_QWORD *)(a3 + 32) = 7;
        *(_WORD *)(a3 + 8) = 0;
        v13 = *(_BYTE *)(a3 + 56);
        *(_QWORD *)v10 = &web::json::details::_String::`vftable';
        *(_OWORD *)(v10 + 8) = v11;
        *(_OWORD *)(v10 + 24) = v12;
        v10[40] = v13;
      }
      else
      {
        v10 = 0;
      }
      v28 = v10;
      web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v10;
        return a2;
      }
      v14 = (char *)operator new(8u);
      v28 = v14;
      if ( v14 )
        *(_QWORD *)v14 = &web::json::details::_Null::`vftable';
      else
        v14 = 0;
      *a2 = v14;
      goto LABEL_45;
    case 8:
      v20 = (char *)operator new(0x18u);
      v10 = v20;
      v28 = v20;
      if ( v20 )
      {
        v21 = *(_QWORD *)(a3 + 56);
        *(_QWORD *)v20 = &web::json::details::_Number::`vftable';
        *((_QWORD *)v20 + 1) = v21;
        *((_DWORD *)v20 + 4) = 2;
      }
      else
      {
        v10 = 0;
      }
      v28 = v10;
      web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v10;
        return a2;
      }
      v22 = (char *)operator new(8u);
      v28 = v22;
      if ( v22 )
        *(_QWORD *)v22 = &web::json::details::_Null::`vftable';
      else
        v22 = 0;
      *a2 = v22;
      goto LABEL_45;
    case 9:
      v28 = 0;
      if ( *(_BYTE *)(a3 + 64) )
      {
        v16 = (char *)operator new(0x18u);
        v28 = v16;
        if ( v16 )
        {
          v17 = *(_QWORD *)(a3 + 56);
          *(_QWORD *)v16 = &web::json::details::_Number::`vftable';
          *((_QWORD *)v16 + 1) = v17;
          *((_DWORD *)v16 + 4) = v17 >= 0;
          goto LABEL_21;
        }
      }
      else
      {
        v16 = (char *)operator new(0x18u);
        v28 = v16;
        if ( v16 )
        {
          v18 = *(_QWORD *)(a3 + 56);
          *(_QWORD *)v16 = &web::json::details::_Number::`vftable';
          *((_QWORD *)v16 + 1) = v18;
          *((_DWORD *)v16 + 4) = 1;
          goto LABEL_21;
        }
      }
      v16 = 0;
LABEL_21:
      v28 = v16;
      web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v16;
        return a2;
      }
      v19 = (char *)operator new(8u);
      v28 = v19;
      if ( v19 )
        *(_QWORD *)v19 = &web::json::details::_Null::`vftable';
      else
        v19 = 0;
      *a2 = v19;
      if ( v16 )
      {
        v9 = *(_QWORD *)v16;
        v8 = v16;
        goto LABEL_47;
      }
      return a2;
    case 0xA:
      v10 = (char *)operator new(0x10u);
      v28 = v10;
      if ( v10 )
      {
        v23 = *(_BYTE *)(a3 + 56);
        *(_QWORD *)v10 = &web::json::details::_Boolean::`vftable';
        v10[8] = v23;
      }
      else
      {
        v10 = 0;
      }
      v28 = v10;
      web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
      if ( *(_DWORD *)(a3 + 72) )
      {
        v24 = (char *)operator new(8u);
        v28 = v24;
        if ( v24 )
          *(_QWORD *)v24 = &web::json::details::_Null::`vftable';
        else
          v24 = 0;
        *a2 = v24;
LABEL_45:
        if ( v10 )
        {
          v9 = *(_QWORD *)v10;
          v8 = v10;
LABEL_47:
          (*(void (__fastcall **)(char *, __int64))(v9 + 192))(v8, 1);
          return a2;
        }
        else
        {
          return a2;
        }
      }
      else
      {
        *a2 = v10;
        return a2;
      }
    case 0xB:
      web::json::details::JSON_Parser<unsigned short>::GetNextToken(a1, a3);
      goto LABEL_50;
    default:
      v25 = web::json::details::json_error_category(a1);
      *(_DWORD *)(a3 + 72) = 8;
      *(_DWORD *)(a3 + 76) = v27;
      *(_QWORD *)(a3 + 80) = v25;
LABEL_50:
      v26 = (char *)operator new(8u);
      v28 = v26;
      if ( v26 )
        *(_QWORD *)v26 = &web::json::details::_Null::`vftable';
      else
        v26 = 0;
      *a2 = v26;
      return a2;
  }
}

```

## disassembly

```asm
0x14000a3c0  push    rbx
0x14000a3c2  push    rbp
0x14000a3c3  push    rsi
0x14000a3c4  push    rdi
0x14000a3c5  push    r14
0x14000a3c7  push    r15
0x14000a3c9  sub     rsp, 58h
0x14000a3cd  mov     rsi, r8
0x14000a3d0  mov     rdi, rdx
0x14000a3d3  mov     rbp, rcx
0x14000a3d6  xor     r15d, r15d
0x14000a3d9  mov     eax, [r8]
0x14000a3dc  dec     eax; switch 11 cases
0x14000a3de  cmp     eax, 0Ah
0x14000a3e1  ja      def_14000A3FB; jumptable 000000014000A3FB default case, cases 2,4-6
0x14000a3e7  cdqe
0x14000a3e9  lea     rcx, __ImageBase
0x14000a3f0  mov     r9d, ds:(jpt_14000A3FB - 140000000h)[rcx+rax*4]
0x14000a3f8  add     r9, rcx
0x14000a3fb  jmp     r9; switch jump
0x14000a3fe  lea     rdx, [rsp+88h+arg_10]; jumptable 000000014000A3FB case 1
0x14000a406  mov     rcx, rbp
0x14000a409  call    ?_ParseObject@?$JSON_Parser@G@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::_ParseObject(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a40e  mov     rcx, [rax]
0x14000a411  mov     [rax], r15
0x14000a414  mov     [rdi], rcx
0x14000a417  mov     rcx, [rsp+88h+arg_10]
0x14000a41f  test    rcx, rcx
0x14000a422  jz      loc_14000A769
0x14000a428  mov     rax, [rcx]
0x14000a42b  jmp     loc_14000A6E8
0x14000a430  lea     rdx, [rsp+88h+arg_10]; jumptable 000000014000A3FB case 3
0x14000a438  mov     rcx, rbp
0x14000a43b  call    ?_ParseArray@?$JSON_Parser@G@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::_ParseArray(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a440  jmp     short loc_14000A40E
0x14000a442  mov     ecx, 30h ; '0'; jumptable 000000014000A3FB case 7
0x14000a447  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a44c  mov     rbx, rax
0x14000a44f  mov     [rsp+88h+arg_10], rax
0x14000a457  test    rax, rax
0x14000a45a  jz      short loc_14000A490
0x14000a45c  movups  xmm0, xmmword ptr [rsi+8]
0x14000a460  movups  xmm1, xmmword ptr [rsi+18h]
0x14000a464  mov     [rsi+18h], r15
0x14000a468  mov     qword ptr [rsi+20h], 7
0x14000a470  mov     [rsi+8], r15w
0x14000a475  movzx   eax, byte ptr [rsi+38h]
0x14000a479  lea     rcx, ??_7_String@details@json@web@@6B@; const web::json::details::_String::`vftable'
0x14000a480  mov     [rbx], rcx
0x14000a483  movups  xmmword ptr [rbx+8], xmm0
0x14000a487  movups  xmmword ptr [rbx+18h], xmm1
0x14000a48b  mov     [rbx+28h], al
0x14000a48e  jmp     short loc_14000A493
0x14000a490  mov     rbx, r15
0x14000a493  mov     [rsp+88h+arg_10], rbx
0x14000a49b  mov     rdx, rsi
0x14000a49e  mov     rcx, rbp
0x14000a4a1  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a4a6  cmp     dword ptr [rsi+48h], 0
0x14000a4aa  jz      short loc_14000A4DA
0x14000a4ac  mov     ecx, 8; Size
0x14000a4b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a4b6  mov     [rsp+88h+arg_10], rax
0x14000a4be  test    rax, rax
0x14000a4c1  jz      short loc_14000A4CF
0x14000a4c3  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x14000a4ca  mov     [rax], rcx
0x14000a4cd  jmp     short loc_14000A4D2
0x14000a4cf  mov     rax, r15
0x14000a4d2  mov     [rdi], rax
0x14000a4d5  jmp     loc_14000A6D9
0x14000a4da  mov     [rdi], rbx
0x14000a4dd  mov     rax, rdi
0x14000a4e0  add     rsp, 58h
0x14000a4e4  pop     r15
0x14000a4e6  pop     r14
0x14000a4e8  pop     rdi
0x14000a4e9  pop     rsi
0x14000a4ea  pop     rbp
0x14000a4eb  pop     rbx
0x14000a4ec  retn
0x14000a4ed  mov     [rsp+88h+arg_10], r15; jumptable 000000014000A3FB case 9
0x14000a4f5  mov     ecx, 18h; Size
0x14000a4fa  cmp     byte ptr [r8+40h], 0
0x14000a4ff  jz      short loc_14000A534
0x14000a501  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a506  mov     rbx, rax
0x14000a509  mov     [rsp+88h+arg_10], rax
0x14000a511  test    rax, rax
0x14000a514  jz      short loc_14000A564
0x14000a516  mov     rax, [rsi+38h]
0x14000a51a  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x14000a521  mov     [rbx], rcx
0x14000a524  mov     [rbx+8], rax
0x14000a528  shr     rax, 3Fh
0x14000a52c  xor     eax, 1
0x14000a52f  mov     [rbx+10h], eax
0x14000a532  jmp     short loc_14000A567
0x14000a534  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a539  mov     rbx, rax
0x14000a53c  mov     [rsp+88h+arg_10], rax
0x14000a544  test    rax, rax
0x14000a547  jz      short loc_14000A564
0x14000a549  mov     rax, [rsi+38h]
0x14000a54d  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x14000a554  mov     [rbx], rcx
0x14000a557  mov     [rbx+8], rax
0x14000a55b  mov     dword ptr [rbx+10h], 1
0x14000a562  jmp     short loc_14000A567
0x14000a564  mov     rbx, r15
0x14000a567  mov     r14, rbx
0x14000a56a  mov     [rsp+88h+arg_10], rbx
0x14000a572  mov     rdx, rsi
0x14000a575  mov     rcx, rbp
0x14000a578  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a57d  cmp     dword ptr [rsi+48h], 0
0x14000a581  jz      short loc_14000A5C0
0x14000a583  mov     ecx, 8; Size
0x14000a588  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a58d  mov     [rsp+88h+arg_10], rax
0x14000a595  test    rax, rax
0x14000a598  jz      short loc_14000A5A6
0x14000a59a  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x14000a5a1  mov     [rax], rcx
0x14000a5a4  jmp     short loc_14000A5A9
0x14000a5a6  mov     rax, r15
0x14000a5a9  mov     [rdi], rax
0x14000a5ac  test    r14, r14
0x14000a5af  jz      loc_14000A769
0x14000a5b5  mov     rax, [r14]
0x14000a5b8  mov     rcx, r14
0x14000a5bb  jmp     loc_14000A6E8
0x14000a5c0  mov     [rdi], rbx
0x14000a5c3  mov     rax, rdi
0x14000a5c6  add     rsp, 58h
0x14000a5ca  pop     r15
0x14000a5cc  pop     r14
0x14000a5ce  pop     rdi
0x14000a5cf  pop     rsi
0x14000a5d0  pop     rbp
0x14000a5d1  pop     rbx
0x14000a5d2  retn
0x14000a5d3  mov     ecx, 18h; jumptable 000000014000A3FB case 8
0x14000a5d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a5dd  mov     rbx, rax
0x14000a5e0  mov     [rsp+88h+arg_10], rax
0x14000a5e8  test    rax, rax
0x14000a5eb  jz      short loc_14000A60A
0x14000a5ed  movsd   xmm0, qword ptr [rsi+38h]
0x14000a5f2  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x14000a5f9  mov     [rax], rcx
0x14000a5fc  movsd   qword ptr [rax+8], xmm0
0x14000a601  mov     dword ptr [rax+10h], 2
0x14000a608  jmp     short loc_14000A60D
0x14000a60a  mov     rbx, r15
0x14000a60d  mov     [rsp+88h+arg_10], rbx
0x14000a615  mov     rdx, rsi
0x14000a618  mov     rcx, rbp
0x14000a61b  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a620  cmp     dword ptr [rsi+48h], 0
0x14000a624  jz      short loc_14000A654
0x14000a626  mov     ecx, 8; Size
0x14000a62b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a630  mov     [rsp+88h+arg_10], rax
0x14000a638  test    rax, rax
0x14000a63b  jz      short loc_14000A649
0x14000a63d  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x14000a644  mov     [rax], rcx
0x14000a647  jmp     short loc_14000A64C
0x14000a649  mov     rax, r15
0x14000a64c  mov     [rdi], rax
0x14000a64f  jmp     loc_14000A6D9
0x14000a654  mov     [rdi], rbx
0x14000a657  mov     rax, rdi
0x14000a65a  add     rsp, 58h
0x14000a65e  pop     r15
0x14000a660  pop     r14
0x14000a662  pop     rdi
0x14000a663  pop     rsi
0x14000a664  pop     rbp
0x14000a665  pop     rbx
0x14000a666  retn
0x14000a667  mov     ecx, 10h; jumptable 000000014000A3FB case 10
0x14000a66c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a671  mov     rbx, rax
0x14000a674  mov     [rsp+88h+arg_10], rax
0x14000a67c  test    rax, rax
0x14000a67f  jz      short loc_14000A694
0x14000a681  movzx   eax, byte ptr [rsi+38h]
0x14000a685  lea     rcx, ??_7_Boolean@details@json@web@@6B@; const web::json::details::_Boolean::`vftable'
0x14000a68c  mov     [rbx], rcx
0x14000a68f  mov     [rbx+8], al
0x14000a692  jmp     short loc_14000A697
0x14000a694  mov     rbx, r15
0x14000a697  mov     [rsp+88h+arg_10], rbx
0x14000a69f  mov     rdx, rsi
0x14000a6a2  mov     rcx, rbp
0x14000a6a5  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a6aa  cmp     dword ptr [rsi+48h], 0
0x14000a6ae  jz      short loc_14000A709
0x14000a6b0  mov     ecx, 8; Size
0x14000a6b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a6ba  mov     [rsp+88h+arg_10], rax
0x14000a6c2  test    rax, rax
0x14000a6c5  jz      short loc_14000A6D3
0x14000a6c7  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x14000a6ce  mov     [rax], rcx
0x14000a6d1  jmp     short loc_14000A6D6
0x14000a6d3  mov     rax, r15
0x14000a6d6  mov     [rdi], rax
0x14000a6d9  test    rbx, rbx
0x14000a6dc  jz      loc_14000A769
0x14000a6e2  mov     rax, [rbx]
0x14000a6e5  mov     rcx, rbx
0x14000a6e8  mov     edx, 1
0x14000a6ed  mov     rax, [rax+0C0h]
0x14000a6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6f9  mov     rax, rdi
0x14000a6fc  add     rsp, 58h
0x14000a700  pop     r15
0x14000a702  pop     r14
0x14000a704  pop     rdi
0x14000a705  pop     rsi
0x14000a706  pop     rbp
0x14000a707  pop     rbx
0x14000a708  retn
0x14000a709  mov     [rdi], rbx
0x14000a70c  mov     rax, rdi
0x14000a70f  add     rsp, 58h
0x14000a713  pop     r15
0x14000a715  pop     r14
0x14000a717  pop     rdi
0x14000a718  pop     rsi
0x14000a719  pop     rbp
0x14000a71a  pop     rbx
0x14000a71b  retn
0x14000a71c  mov     rdx, rsi; jumptable 000000014000A3FB case 11
0x14000a71f  mov     rcx, rbp
0x14000a722  call    ?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)
0x14000a727  jmp     short loc_14000A740
0x14000a729  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; jumptable 000000014000A3FB default case, cases 2,4-6
0x14000a72e  mov     dword ptr [rsi+48h], 8
0x14000a735  mov     ecx, [rsp+88h+var_5C]
0x14000a739  mov     [rsi+4Ch], ecx
0x14000a73c  mov     [rsi+50h], rax
0x14000a740  mov     ecx, 8; Size
0x14000a745  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000a74a  mov     [rsp+88h+arg_10], rax
0x14000a752  test    rax, rax
0x14000a755  jz      short loc_14000A763
0x14000a757  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x14000a75e  mov     [rax], rcx
0x14000a761  jmp     short loc_14000A766
0x14000a763  mov     rax, r15
0x14000a766  mov     [rdi], rax
0x14000a769  mov     rax, rdi
0x14000a76c  add     rsp, 58h
0x14000a770  pop     r15
0x14000a772  pop     r14
0x14000a774  pop     rdi
0x14000a775  pop     rsi
0x14000a776  pop     rbp
0x14000a777  pop     rbx
0x14000a778  retn
```
