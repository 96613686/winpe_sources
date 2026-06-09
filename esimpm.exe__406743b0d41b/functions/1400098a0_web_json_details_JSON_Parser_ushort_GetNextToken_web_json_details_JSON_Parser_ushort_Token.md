# web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x1400098a0`
- end: `0x140009c60`
- name: `?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z`
- size: `960`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008af0`
- `0x140009db0`
- `0x140009f80`
- `0x14000a3c0`

## callees

- `0x140007f60`
- `0x140008ef0`
- `0x1400098a0`
- `0x14003e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1400098ea`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1400098ea`

## pseudocode

```c
char __fastcall web::json::details::JSON_Parser<unsigned short>::GetNextToken(int *a1, __int64 a2)
{
  web::json::details *v3; // rsi
  unsigned __int16 i; // bp
  web::json::details *v6; // rcx
  const struct web::json::details::json_error_category_impl *v7; // rax
  web::json::details *v8; // rcx
  int v9; // ecx
  int v10; // ecx
  web::json::details *v11; // rcx
  web::json::details *v12; // rcx
  web::json::details *v13; // rcx
  int v15; // [rsp+24h] [rbp-44h]

  v3 = (web::json::details *)(a2 + 8);
  while ( 2 )
  {
    for ( i = (**(__int64 (__fastcall ***)(int *))a1)(a1); i != 0xFFFF; i = (**(__int64 (__fastcall ***)(int *))a1)(a1) )
    {
      if ( !(unsigned int)_o_iswspace(i) )
        break;
    }
    *(_DWORD *)a2 = 0;
    v6 = v3;
    *(_QWORD *)(a2 + 40) = *((_QWORD *)a1 + 1);
    v7 = (const struct web::json::details::json_error_category_impl *)*((_QWORD *)a1 + 2);
    *(_QWORD *)(a2 + 48) = v7;
    *(_QWORD *)(a2 + 24) = 0;
    if ( *(_QWORD *)(a2 + 32) > 7u )
      v6 = *(web::json::details **)v3;
    *(_WORD *)v6 = 0;
    if ( i != 0xFFFF )
    {
      LOBYTE(v7) = i - 34;
      switch ( i )
      {
        case '"':
          LOBYTE(v7) = (*(__int64 (__fastcall **)(int *, __int64))(*(_QWORD *)a1 + 24LL))(a1, a2);
          if ( !(_BYTE)v7 )
          {
            v7 = web::json::details::json_error_category(v12);
            *(_DWORD *)(a2 + 72) = 7;
            goto LABEL_46;
          }
          return (char)v7;
        case ',':
          *(_DWORD *)a2 = 5;
          goto LABEL_16;
        case '-':
        case '0':
        case '1':
        case '2':
        case '3':
        case '4':
        case '5':
        case '6':
        case '7':
        case '8':
        case '9':
          LOBYTE(v7) = web::json::details::JSON_Parser<unsigned short>::CompleteNumberLiteral((__int64)a1, i, a2);
          if ( (_BYTE)v7 )
            return (char)v7;
          v7 = web::json::details::json_error_category(v13);
          *(_DWORD *)(a2 + 72) = 6;
          goto LABEL_46;
        case '/':
          if ( (*(unsigned __int8 (__fastcall **)(int *, __int64))(*(_QWORD *)a1 + 16LL))(a1, a2) )
            continue;
          v7 = web::json::details::json_error_category(v8);
          *(_DWORD *)(a2 + 72) = 3;
          goto LABEL_46;
        case ':':
          *(_DWORD *)a2 = 6;
          goto LABEL_16;
        case '[':
        case '{':
          if ( ++*((_QWORD *)a1 + 3) > 0x80u )
          {
            v7 = web::json::details::json_error_category(v6);
            *(_DWORD *)(a2 + 72) = 10;
            goto LABEL_46;
          }
          v9 = 3;
          LOBYTE(v7) = 1;
          if ( i == 123 )
            v9 = 1;
          *(_DWORD *)a2 = v9;
LABEL_16:
          *((_QWORD *)v3 + 2) = 0;
          if ( *((_QWORD *)v3 + 3) > 7u )
            v3 = *(web::json::details **)v3;
          goto LABEL_18;
        case ']':
        case '}':
          --*((_QWORD *)a1 + 3);
          if ( a1[6] < 0 )
          {
            v7 = web::json::details::json_error_category(v6);
            *(_DWORD *)(a2 + 72) = 9;
            goto LABEL_46;
          }
          v10 = 4;
          LOBYTE(v7) = 2;
          if ( i == 125 )
            v10 = 2;
          *(_DWORD *)a2 = v10;
          *((_QWORD *)v3 + 2) = 0;
          if ( *((_QWORD *)v3 + 3) <= 7u )
LABEL_18:
            *(_WORD *)v3 = 0;
          else
            **(_WORD **)v3 = 0;
          break;
        case 'f':
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 97 )
            goto LABEL_31;
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 108 )
            goto LABEL_31;
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 115 )
            goto LABEL_31;
          LOWORD(v7) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_WORD)v7 != 101 )
            goto LABEL_31;
          *(_DWORD *)a2 = 10;
          *(_BYTE *)(a2 + 56) = 0;
          return (char)v7;
        case 'n':
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 117 )
            goto LABEL_31;
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 108 )
            goto LABEL_31;
          LOWORD(v7) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_WORD)v7 != 108 )
            goto LABEL_31;
          *(_DWORD *)a2 = 11;
          return (char)v7;
        case 't':
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 114
            && (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 117
            && (LOWORD(v7) = (**(__int64 (__fastcall ***)(int *))a1)(a1), (_WORD)v7 == 101) )
          {
            *(_DWORD *)a2 = 10;
            *(_BYTE *)(a2 + 56) = 1;
          }
          else
          {
LABEL_31:
            v7 = web::json::details::json_error_category(v11);
            *(_DWORD *)(a2 + 72) = 4;
LABEL_46:
            *(_DWORD *)(a2 + 76) = v15;
            *(_QWORD *)(a2 + 80) = v7;
          }
          break;
        default:
          v7 = web::json::details::json_error_category(v6);
          *(_DWORD *)(a2 + 72) = 8;
          goto LABEL_46;
      }
    }
    return (char)v7;
  }
}

```

## disassembly

```asm
0x1400098a0  push    rbx
0x1400098a2  push    rbp
0x1400098a3  push    rsi
0x1400098a4  push    rdi
0x1400098a5  push    r12
0x1400098a7  push    r14
0x1400098a9  push    r15
0x1400098ab  sub     rsp, 30h
0x1400098af  mov     rbx, rdx
0x1400098b2  lea     rsi, [rdx+8]
0x1400098b6  mov     rdi, rcx
0x1400098b9  lea     r12, __ImageBase
0x1400098c0  mov     r15d, 0FFFFh
0x1400098c6  xor     r14d, r14d
0x1400098c9  nop     dword ptr [rax+00000000h]
0x1400098d0  mov     rax, [rdi]
0x1400098d3  mov     rcx, rdi
0x1400098d6  mov     rax, [rax]
0x1400098d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098de  movzx   ebp, ax
0x1400098e1  cmp     ax, r15w
0x1400098e5  jz      short loc_14000990B
0x1400098e7  movzx   ecx, bp
0x1400098ea  call    cs:__imp__o_iswspace
0x1400098f0  test    eax, eax
0x1400098f2  jz      short loc_14000990B
0x1400098f4  mov     rax, [rdi]
0x1400098f7  mov     rcx, rdi
0x1400098fa  mov     rax, [rax]
0x1400098fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009902  movzx   ebp, ax
0x140009905  cmp     ax, r15w
0x140009909  jnz     short loc_1400098E7
0x14000990b  mov     [rbx], r14d
0x14000990e  mov     rcx, rsi
0x140009911  mov     rax, [rdi+8]
0x140009915  mov     [rbx+28h], rax
0x140009919  mov     rax, [rdi+10h]
0x14000991d  mov     [rbx+30h], rax
0x140009921  mov     [rbx+18h], r14
0x140009925  cmp     qword ptr [rbx+20h], 7
0x14000992a  jbe     short loc_14000992F
0x14000992c  mov     rcx, [rsi]; this
0x14000992f  mov     [rcx], r14w
0x140009933  cmp     bp, r15w
0x140009937  jz      loc_140009BC8
0x14000993d  movzx   eax, bp
0x140009940  add     eax, 0FFFFFFDEh; switch 92 cases
0x140009943  cmp     eax, 5Bh
0x140009946  ja      def_140009962; jumptable 0000000140009962 default case, cases 35-43,46,59-90,92,94-101,103-109,111-115,117-122,124
0x14000994c  cdqe
0x14000994e  movzx   eax, ds:(byte_140009C04 - 140000000h)[r12+rax]
0x140009957  mov     ecx, ds:(jpt_140009962 - 140000000h)[r12+rax*4]
0x14000995f  add     rcx, r12; this
0x140009962  jmp     rcx; switch jump
0x140009964  mov     rax, [rdi]; jumptable 0000000140009962 case 47
0x140009967  mov     rdx, rbx
0x14000996a  mov     rcx, rdi
0x14000996d  mov     rax, [rax+10h]
0x140009971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009976  test    al, al
0x140009978  jnz     loc_1400098D0
0x14000997e  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x140009983  mov     dword ptr [rbx+48h], 3
0x14000998a  jmp     loc_140009BBD
0x14000998f  inc     qword ptr [rdi+18h]; jumptable 0000000140009962 cases 91,123
0x140009993  cmp     qword ptr [rdi+18h], 80h
0x14000999b  jbe     short loc_1400099AE
0x14000999d  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x1400099a2  mov     dword ptr [rbx+48h], 0Ah
0x1400099a9  jmp     loc_140009BBD
0x1400099ae  cmp     bp, 7Bh ; '{'
0x1400099b2  mov     ecx, 3
0x1400099b7  mov     eax, 1
0x1400099bc  cmovz   ecx, eax
0x1400099bf  mov     [rbx], ecx
0x1400099c1  mov     [rsi+10h], r14
0x1400099c5  cmp     qword ptr [rsi+18h], 7
0x1400099ca  jbe     short loc_1400099CF
0x1400099cc  mov     rsi, [rsi]
0x1400099cf  mov     [rsi], r14w
0x1400099d3  add     rsp, 30h
0x1400099d7  pop     r15
0x1400099d9  pop     r14
0x1400099db  pop     r12
0x1400099dd  pop     rdi
0x1400099de  pop     rsi
0x1400099df  pop     rbp
0x1400099e0  pop     rbx
0x1400099e1  retn
0x1400099e2  dec     qword ptr [rdi+18h]; jumptable 0000000140009962 cases 93,125
0x1400099e6  cmp     [rdi+18h], r14d
0x1400099ea  jge     short loc_1400099FD
0x1400099ec  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x1400099f1  mov     dword ptr [rbx+48h], 9
0x1400099f8  jmp     loc_140009BBD
0x1400099fd  cmp     bp, 7Dh ; '}'
0x140009a01  mov     ecx, 4
0x140009a06  mov     eax, 2
0x140009a0b  cmovz   ecx, eax
0x140009a0e  mov     [rbx], ecx
0x140009a10  mov     [rsi+10h], r14
0x140009a14  cmp     qword ptr [rsi+18h], 7
0x140009a19  jbe     short loc_1400099CF
0x140009a1b  mov     rsi, [rsi]
0x140009a1e  mov     [rsi], r14w
0x140009a22  add     rsp, 30h
0x140009a26  pop     r15
0x140009a28  pop     r14
0x140009a2a  pop     r12
0x140009a2c  pop     rdi
0x140009a2d  pop     rsi
0x140009a2e  pop     rbp
0x140009a2f  pop     rbx
0x140009a30  retn
0x140009a31  mov     dword ptr [rbx], 5; jumptable 0000000140009962 case 44
0x140009a37  jmp     short loc_1400099C1
0x140009a39  mov     dword ptr [rbx], 6; jumptable 0000000140009962 case 58
0x140009a3f  jmp     short loc_1400099C1
0x140009a41  mov     rax, [rdi]; jumptable 0000000140009962 case 116
0x140009a44  mov     rcx, rdi
0x140009a47  mov     rax, [rax]
0x140009a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a4f  cmp     ax, 72h ; 'r'
0x140009a53  jnz     short loc_140009A96
0x140009a55  mov     rax, [rdi]
0x140009a58  mov     rcx, rdi
0x140009a5b  mov     rax, [rax]
0x140009a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a63  cmp     ax, 75h ; 'u'
0x140009a67  jnz     short loc_140009A96
0x140009a69  mov     rax, [rdi]
0x140009a6c  mov     rcx, rdi
0x140009a6f  mov     rax, [rax]
0x140009a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a77  cmp     ax, 65h ; 'e'
0x140009a7b  jnz     short loc_140009A96
0x140009a7d  mov     dword ptr [rbx], 0Ah
0x140009a83  mov     byte ptr [rbx+38h], 1
0x140009a87  add     rsp, 30h
0x140009a8b  pop     r15
0x140009a8d  pop     r14
0x140009a8f  pop     r12
0x140009a91  pop     rdi
0x140009a92  pop     rsi
0x140009a93  pop     rbp
0x140009a94  pop     rbx
0x140009a95  retn
0x140009a96  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x140009a9b  mov     dword ptr [rbx+48h], 4
0x140009aa2  jmp     loc_140009BBD
0x140009aa7  mov     rax, [rdi]; jumptable 0000000140009962 case 102
0x140009aaa  mov     rcx, rdi
0x140009aad  mov     rax, [rax]
0x140009ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ab5  cmp     ax, 61h ; 'a'
0x140009ab9  jnz     short loc_140009A96
0x140009abb  mov     rax, [rdi]
0x140009abe  mov     rcx, rdi
0x140009ac1  mov     rax, [rax]
0x140009ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ac9  cmp     ax, 6Ch ; 'l'
0x140009acd  jnz     short loc_140009A96
0x140009acf  mov     rax, [rdi]
0x140009ad2  mov     rcx, rdi
0x140009ad5  mov     rax, [rax]
0x140009ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009add  cmp     ax, 73h ; 's'
0x140009ae1  jnz     short loc_140009A96
0x140009ae3  mov     rax, [rdi]
0x140009ae6  mov     rcx, rdi
0x140009ae9  mov     rax, [rax]
0x140009aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009af1  cmp     ax, 65h ; 'e'
0x140009af5  jnz     short loc_140009A96
0x140009af7  mov     dword ptr [rbx], 0Ah
0x140009afd  mov     [rbx+38h], r14b
0x140009b01  add     rsp, 30h
0x140009b05  pop     r15
0x140009b07  pop     r14
0x140009b09  pop     r12
0x140009b0b  pop     rdi
0x140009b0c  pop     rsi
0x140009b0d  pop     rbp
0x140009b0e  pop     rbx
0x140009b0f  retn
0x140009b10  mov     rax, [rdi]; jumptable 0000000140009962 case 110
0x140009b13  mov     rcx, rdi
0x140009b16  mov     rax, [rax]
0x140009b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b1e  cmp     ax, 75h ; 'u'
0x140009b22  jnz     loc_140009A96
0x140009b28  mov     rax, [rdi]
0x140009b2b  mov     rcx, rdi
0x140009b2e  mov     rax, [rax]
0x140009b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b36  cmp     ax, 6Ch ; 'l'
0x140009b3a  jnz     loc_140009A96
0x140009b40  mov     rax, [rdi]
0x140009b43  mov     rcx, rdi
0x140009b46  mov     rax, [rax]
0x140009b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b4e  cmp     ax, 6Ch ; 'l'
0x140009b52  jnz     loc_140009A96
0x140009b58  mov     dword ptr [rbx], 0Bh
0x140009b5e  add     rsp, 30h
0x140009b62  pop     r15
0x140009b64  pop     r14
0x140009b66  pop     r12
0x140009b68  pop     rdi
0x140009b69  pop     rsi
0x140009b6a  pop     rbp
0x140009b6b  pop     rbx
0x140009b6c  retn
0x140009b6d  mov     rax, [rdi]; jumptable 0000000140009962 case 34
0x140009b70  mov     rdx, rbx
0x140009b73  mov     rcx, rdi
0x140009b76  mov     rax, [rax+18h]
0x140009b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b7f  test    al, al
0x140009b81  jnz     short loc_140009BC8
0x140009b83  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x140009b88  mov     dword ptr [rbx+48h], 7
0x140009b8f  jmp     short loc_140009BBD
0x140009b91  mov     r8, rbx; jumptable 0000000140009962 cases 45,48-57
0x140009b94  movzx   edx, bp
0x140009b97  mov     rcx, rdi
0x140009b9a  call    ?CompleteNumberLiteral@?$JSON_Parser@G@details@json@web@@AEAA_NGAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::CompleteNumberLiteral(ushort,web::json::details::JSON_Parser<ushort>::Token &)
0x140009b9f  test    al, al
0x140009ba1  jnz     short loc_140009BC8
0x140009ba3  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x140009ba8  mov     dword ptr [rbx+48h], 6
0x140009baf  jmp     short loc_140009BBD
0x140009bb1  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; jumptable 0000000140009962 default case, cases 35-43,46,59-90,92,94-101,103-109,111-115,117-122,124
0x140009bb6  mov     dword ptr [rbx+48h], 8
0x140009bbd  mov     ecx, [rsp+68h+var_44]
0x140009bc1  mov     [rbx+4Ch], ecx
0x140009bc4  mov     [rbx+50h], rax
0x140009bc8  add     rsp, 30h
0x140009bcc  pop     r15
0x140009bce  pop     r14
0x140009bd0  pop     r12
0x140009bd2  pop     rdi
0x140009bd3  pop     rsi
0x140009bd4  pop     rbp
0x140009bd5  pop     rbx
0x140009bd6  retn
```
