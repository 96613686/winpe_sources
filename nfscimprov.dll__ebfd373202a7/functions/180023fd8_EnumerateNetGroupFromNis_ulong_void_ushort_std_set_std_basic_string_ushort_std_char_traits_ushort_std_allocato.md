# EnumerateNetGroupFromNis(ulong (*)(void *,ushort *,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &),void *,ushort *,ushort *,CNfsTaskContext *)

- ea: `0x180023fd8`
- end: `0x18002442c`
- name: `?EnumerateNetGroupFromNis@@YAKP6AKPEAXPEAGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z011PEAVCNfsTaskContext@@@Z`
- size: `1108`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x180014c58`
- `0x1800152bc`
- `0x1800156bc`

## callees

- `0x180009670`
- `0x180014e50`
- `0x180018230`
- `0x1800182b8`
- `0x180023fd8`
- `0x1800252d8`
- `0x1800292f8`
- `0x18002db9c`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `msvcrt!free` at `0x1800240d4`
- `msvcrt!free` at `0x180024155`
- `msvcrt!free` at `0x180024195`
- `msvcrt!free` at `0x1800240d4`
- `msvcrt!free` at `0x180024155`
- `msvcrt!free` at `0x180024195`
- `ntdll!RtlInitUnicodeString` at `0x18002405b`
- `ntdll!RtlInitUnicodeString` at `0x1800242f5`
- `ntdll!RtlInitUnicodeString` at `0x18002405b`
- `ntdll!RtlInitUnicodeString` at `0x1800242f5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002426b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180024350`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002426b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180024350`
- `KERNEL32!HeapFree` at `0x1800242e8`
- `KERNEL32!HeapFree` at `0x1800242e8`
- `KERNEL32!HeapAlloc` at `0x180024319`
- `KERNEL32!HeapAlloc` at `0x180024319`
- `KERNEL32!GetProcessHeap` at `0x1800242da`
- `KERNEL32!GetProcessHeap` at `0x180024308`
- `KERNEL32!GetProcessHeap` at `0x1800242da`
- `KERNEL32!GetProcessHeap` at `0x180024308`
- `WS2_32!__imp_getprotobyname` at `0x180024078`
- `WS2_32!__imp_getprotobyname` at `0x1800240fb`
- `WS2_32!__imp_getprotobyname` at `0x180024078`
- `WS2_32!__imp_getprotobyname` at `0x1800240fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EnumerateNetGroupFromNis(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  char *v8; // rdi
  struct protoent *v9; // rax
  __int64 num; // r14
  char *v11; // rdi
  struct protoent *v12; // rax
  int v13; // edi
  __int128 *i; // rsi
  int v15; // eax
  CHAR *v16; // rcx
  bool v17; // zf
  NTSTATUS v18; // eax
  CHAR *v19; // rcx
  bool v20; // zf
  USHORT Length; // ax
  PWSTR Buffer; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v24; // rbx
  HANDLE v25; // rax
  NTSTATUS v26; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _STRING SourceString; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v30; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v31; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[16]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v33; // [rsp+90h] [rbp-70h] BYREF
  __int128 v34; // [rsp+A0h] [rbp-60h]
  __int128 v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+C0h] [rbp-40h]
  void *Block; // [rsp+D0h] [rbp-30h] BYREF
  char v38; // [rsp+D8h] [rbp-28h] BYREF
  void *v39; // [rsp+160h] [rbp+60h] BYREF
  char v40; // [rsp+168h] [rbp+68h] BYREF
  void *v41; // [rsp+1F0h] [rbp+F0h] BYREF
  char v42; // [rsp+1F8h] [rbp+F8h] BYREF
  char v43; // [rsp+280h] [rbp+180h] BYREF

  v31 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  SourceString = 0;
  *(_QWORD *)&v30.Length = 134219774;
  v30.Buffer = (PWSTR)&v43;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v8 = *(char **)ATL::CW2AEX<128>::CW2AEX<128>(&Block, a3);
  v9 = getprotobyname("tcp");
  if ( !v9 )
  {
    rpc_createerr = 17;
LABEL_3:
    dword_180056908 = -1;
    num = 0;
    goto LABEL_8;
  }
  if ( v9->p_proto != 6 && v9->p_proto != 17 )
  {
    rpc_createerr = 12;
    goto LABEL_3;
  }
  num = nfsoncrpc_clnt_create_num(v8);
LABEL_8:
  if ( Block != &v38 )
    free(Block);
  if ( num )
    goto LABEL_22;
  v11 = *(char **)ATL::CW2AEX<128>::CW2AEX<128>(&v39, a3);
  v12 = getprotobyname("udp");
  if ( !v12 )
  {
    rpc_createerr = 17;
LABEL_13:
    dword_180056908 = -1;
    num = 0;
    goto LABEL_18;
  }
  if ( v12->p_proto != 6 && v12->p_proto != 17 )
  {
    rpc_createerr = 12;
    goto LABEL_13;
  }
  num = nfsoncrpc_clnt_create_num(v11);
LABEL_18:
  if ( v39 != &v40 )
    free(v39);
  if ( !num )
    return 1232;
LABEL_22:
  *(_QWORD *)&v31 = *(_QWORD *)ATL::CW2AEX<128>::CW2AEX<128>(&v41, a4);
  if ( v41 != &v42 )
    free(v41);
  *((_QWORD *)&v31 + 1) = "netgroup";
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  if ( (**(unsigned int (__fastcall ***)(__int64, __int64, __int64 (__fastcall *)(), __int128 *, __int64 (__fastcall *)(), __int128 *, __int64))(num + 8))(
         num,
         8,
         xdr_ypreq_nokey,
         &v31,
         xdr_ypresp_all_list,
         &v33,
         250) )
  {
    v13 = 1726;
  }
  else
  {
    v13 = 0;
    for ( i = &v33; i && *(_DWORD *)i; i = (__int128 *)*((_QWORD *)i + 6) )
    {
      v15 = *((_DWORD *)i + 2);
      if ( v15 != 1 )
      {
        if ( v15 != 2 )
          v13 = 87;
        break;
      }
      v16 = (CHAR *)*((_QWORD *)i + 5);
      if ( v16 && *((_DWORD *)i + 8) )
      {
        v17 = v13 == 0;
        if ( v13 >= 0 )
        {
          SourceString.Length = *((_WORD *)i + 16);
          SourceString.MaximumLength = SourceString.Length;
          SourceString.Buffer = v16;
          v18 = RtlAnsiStringToUnicodeString(&v30, &SourceString, 0);
          if ( v18 >= 0 )
            v30.Buffer[(unsigned __int64)v30.Length >> 1] = 0;
          else
            v13 = v18 | 0x10000000;
          v17 = v13 == 0;
        }
        if ( !v17 )
          break;
      }
      v19 = (CHAR *)*((_QWORD *)i + 3);
      if ( v19 && *((_DWORD *)i + 8) )
      {
        v20 = v13 == 0;
        if ( v13 >= 0 )
        {
          Length = *((_WORD *)i + 8);
          SourceString.Length = Length;
          SourceString.MaximumLength = Length;
          SourceString.Buffer = v19;
          if ( DestinationString.MaximumLength < Length )
          {
            Buffer = DestinationString.Buffer;
            if ( DestinationString.Buffer )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, Buffer);
              RtlInitUnicodeString(&DestinationString, 0);
              Length = SourceString.Length;
            }
            v24 = 2LL * ((unsigned int)Length + 1);
            v25 = GetProcessHeap();
            DestinationString.Buffer = (PWSTR)HeapAlloc(v25, 8u, v24);
            if ( !DestinationString.Buffer )
            {
              v13 = 8;
              break;
            }
            DestinationString.MaximumLength = 2 * (SourceString.Length + 1);
            DestinationString.Length = 0;
          }
          v26 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 0);
          if ( v26 >= 0 )
            DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 0;
          else
            v13 = v26 | 0x10000000;
          if ( v13 )
            break;
          std::set<std::wstring>::set<std::wstring>(v32);
          if ( (unsigned int)ParseHost(DestinationString.Buffer, v32) )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 8LL))(a5, 2147487777LL);
          else
            v13 = EnumNetGroupCallBack(a2, v30.Buffer, v32);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v32);
          v20 = v13 == 0;
        }
        if ( !v20 )
          break;
      }
    }
    free_ypproc_all_2_result(&v33);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(num + 8) + 32LL))(num);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180023fd8  mov     [rsp-8+arg_0], rbx
0x180023fdd  push    rbp
0x180023fde  push    rsi
0x180023fdf  push    rdi
0x180023fe0  push    r12
0x180023fe2  push    r13
0x180023fe4  push    r14
0x180023fe6  push    r15
0x180023fe8  lea     rbp, [rsp-990h]
0x180023ff0  sub     rsp, 0A90h
0x180023ff7  mov     rax, cs:__security_cookie
0x180023ffe  xor     rax, rsp
0x180024001  mov     [rbp+9C0h+var_40], rax
0x180024008  mov     r15, r9
0x18002400b  mov     rsi, r8
0x18002400e  mov     r13, rdx
0x180024011  mov     r12, [rbp+9C0h+arg_20]
0x180024018  xorps   xmm0, xmm0
0x18002401b  movups  [rsp+0AC0h+var_A50], xmm0
0x180024020  xorps   xmm1, xmm1
0x180024023  xor     eax, eax
0x180024025  movups  [rbp+9C0h+var_A30], xmm1
0x180024029  movups  [rbp+9C0h+var_A20], xmm1
0x18002402d  movups  [rbp+9C0h+var_A10], xmm1
0x180024031  mov     [rbp+9C0h+var_A00], rax
0x180024035  movups  xmmword ptr [rsp+0AC0h+SourceString.Length], xmm0
0x18002403a  mov     qword ptr [rsp+0AC0h+var_A60.Length], 80007FEh
0x180024043  lea     rax, [rbp+9C0h+var_840]
0x18002404a  mov     [rsp+0AC0h+var_A60.Buffer], rax
0x18002404f  movups  xmmword ptr [rsp+0AC0h+DestinationString.Length], xmm0
0x180024054  xor     edx, edx; SourceString
0x180024056  lea     rcx, [rsp+0AC0h+DestinationString]; DestinationString
0x18002405b  call    cs:__imp_RtlInitUnicodeString
0x180024061  mov     rdx, rsi
0x180024064  lea     rcx, [rbp+9C0h+Block]
0x180024068  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x18002406d  nop
0x18002406e  mov     rdi, [rax]
0x180024071  lea     rcx, aTcp_0; "tcp"
0x180024078  call    cs:__imp_getprotobyname
0x18002407e  mov     edx, 6
0x180024083  or      ecx, 0FFFFFFFFh
0x180024086  lea     ebx, [rdx+0Bh]
0x180024089  test    rax, rax
0x18002408c  jnz     short loc_18002409F
0x18002408e  mov     cs:rpc_createerr, ebx
0x180024094  mov     cs:dword_180056908, ecx
0x18002409a  xor     r14d, r14d
0x18002409d  jmp     short loc_1800240C7
0x18002409f  cmp     dx, [rax+10h]
0x1800240a3  jz      short loc_1800240B7
0x1800240a5  cmp     bx, [rax+10h]
0x1800240a9  jz      short loc_1800240B7
0x1800240ab  mov     cs:rpc_createerr, 0Ch
0x1800240b5  jmp     short loc_180024094
0x1800240b7  movsx   r9d, word ptr [rax+10h]
0x1800240bc  mov     rcx, rdi; Source
0x1800240bf  call    nfsoncrpc_clnt_create_num
0x1800240c4  mov     r14, rax
0x1800240c7  mov     rcx, [rbp+9C0h+Block]; Block
0x1800240cb  lea     rax, [rbp+9C0h+var_9E8]
0x1800240cf  cmp     rcx, rax
0x1800240d2  jz      short loc_1800240DB
0x1800240d4  call    cs:__imp_free
0x1800240da  nop
0x1800240db  test    r14, r14
0x1800240de  jnz     loc_18002416B
0x1800240e4  mov     rdx, rsi
0x1800240e7  lea     rcx, [rbp+9C0h+var_960]
0x1800240eb  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x1800240f0  nop
0x1800240f1  mov     rdi, [rax]
0x1800240f4  lea     rcx, aUdp_0; "udp"
0x1800240fb  call    cs:__imp_getprotobyname
0x180024101  test    rax, rax
0x180024104  jnz     short loc_18002411B
0x180024106  mov     cs:rpc_createerr, ebx
0x18002410c  mov     cs:dword_180056908, 0FFFFFFFFh
0x180024116  xor     r14d, r14d
0x180024119  jmp     short loc_180024148
0x18002411b  mov     ecx, 6
0x180024120  cmp     cx, [rax+10h]
0x180024124  jz      short loc_180024138
0x180024126  cmp     bx, [rax+10h]
0x18002412a  jz      short loc_180024138
0x18002412c  mov     cs:rpc_createerr, 0Ch
0x180024136  jmp     short loc_18002410C
0x180024138  movsx   r9d, word ptr [rax+10h]
0x18002413d  mov     rcx, rdi; Source
0x180024140  call    nfsoncrpc_clnt_create_num
0x180024145  mov     r14, rax
0x180024148  mov     rcx, [rbp+9C0h+var_960]; Block
0x18002414c  lea     rax, [rbp+9C0h+var_958]
0x180024150  cmp     rcx, rax
0x180024153  jz      short loc_18002415C
0x180024155  call    cs:__imp_free
0x18002415b  nop
0x18002415c  test    r14, r14
0x18002415f  jnz     short loc_18002416B
0x180024161  mov     edi, 4D0h
0x180024166  jmp     loc_180024400
0x18002416b  mov     rdx, r15
0x18002416e  lea     rcx, [rbp+9C0h+var_8D0]
0x180024175  call    ??0?$CW2AEX@$0IA@@ATL@@QEAA@PEBG@Z; ATL::CW2AEX<128>::CW2AEX<128>(ushort const *)
0x18002417a  mov     rcx, [rax]
0x18002417d  mov     qword ptr [rsp+0AC0h+var_A50], rcx
0x180024182  mov     rcx, [rbp+9C0h+var_8D0]; Block
0x180024189  lea     rax, [rbp+9C0h+var_8C8]
0x180024190  cmp     rcx, rax
0x180024193  jz      short loc_18002419C
0x180024195  call    cs:__imp_free
0x18002419b  nop
0x18002419c  lea     rax, aNetgroup_0; "netgroup"
0x1800241a3  mov     qword ptr [rsp+0AC0h+var_A50+8], rax
0x1800241a8  xorps   xmm0, xmm0
0x1800241ab  xor     eax, eax
0x1800241ad  movups  [rbp+9C0h+var_A30], xmm0
0x1800241b1  movups  [rbp+9C0h+var_A20], xmm0
0x1800241b5  movups  [rbp+9C0h+var_A10], xmm0
0x1800241b9  mov     [rbp+9C0h+var_A00], rax
0x1800241bd  mov     rax, [r14+8]
0x1800241c1  mov     rcx, cs:qword_18004BAB0
0x1800241c8  mov     [rsp+0AC0h+var_A90], rcx
0x1800241cd  lea     rcx, [rbp+9C0h+var_A30]
0x1800241d1  mov     [rsp+0AC0h+var_A98], rcx
0x1800241d6  lea     rcx, xdr_ypresp_all_list
0x1800241dd  mov     [rsp+0AC0h+var_AA0], rcx
0x1800241e2  lea     r9, [rsp+0AC0h+var_A50]
0x1800241e7  lea     r8, xdr_ypreq_nokey
0x1800241ee  mov     edx, 8
0x1800241f3  mov     rcx, r14
0x1800241f6  mov     rax, [rax]
0x1800241f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241fe  xor     r15d, r15d
0x180024201  test    eax, eax
0x180024203  jz      short loc_18002420F
0x180024205  mov     edi, 6BEh
0x18002420a  jmp     loc_1800243F0
0x18002420f  mov     edi, r15d
0x180024212  lea     rsi, [rbp+9C0h+var_A30]
0x180024216  mov     ecx, 1
0x18002421b  test    rsi, rsi
0x18002421e  jz      loc_1800243E7
0x180024224  cmp     [rsi], r15d
0x180024227  jz      loc_1800243E7
0x18002422d  mov     eax, [rsi+8]
0x180024230  cmp     eax, ecx
0x180024232  jnz     loc_1800243DC
0x180024238  mov     rcx, [rsi+28h]
0x18002423c  test    rcx, rcx
0x18002423f  jz      short loc_180024297
0x180024241  cmp     [rsi+20h], r15d
0x180024245  jbe     short loc_180024297
0x180024247  test    edi, edi
0x180024249  js      short loc_180024291
0x18002424b  movzx   eax, word ptr [rsi+20h]
0x18002424f  mov     [rsp+0AC0h+SourceString.Length], ax
0x180024254  mov     [rsp+0AC0h+SourceString.MaximumLength], ax
0x180024259  mov     [rsp+0AC0h+SourceString.Buffer], rcx
0x18002425e  xor     r8d, r8d; AllocateDestinationString
0x180024261  lea     rdx, [rsp+0AC0h+SourceString]; SourceString
0x180024266  lea     rcx, [rsp+0AC0h+var_A60]; DestinationString
0x18002426b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180024271  test    eax, eax
0x180024273  jns     short loc_18002427D
0x180024275  mov     edi, eax
0x180024277  bts     edi, 1Ch
0x18002427b  jmp     short loc_18002428F
0x18002427d  movzx   edx, [rsp+0AC0h+var_A60.Length]
0x180024282  shr     rdx, 1
0x180024285  mov     rax, [rsp+0AC0h+var_A60.Buffer]
0x18002428a  mov     [rax+rdx*2], r15w
0x18002428f  test    edi, edi
0x180024291  jnz     loc_1800243E7
0x180024297  mov     rcx, [rsi+18h]
0x18002429b  test    rcx, rcx
0x18002429e  jz      loc_1800243CC
0x1800242a4  cmp     [rsi+20h], r15d
0x1800242a8  jbe     loc_1800243CC
0x1800242ae  test    edi, edi
0x1800242b0  js      loc_1800243CA
0x1800242b6  movzx   eax, word ptr [rsi+10h]
0x1800242ba  mov     [rsp+0AC0h+SourceString.Length], ax
0x1800242bf  mov     [rsp+0AC0h+SourceString.MaximumLength], ax
0x1800242c4  mov     [rsp+0AC0h+SourceString.Buffer], rcx
0x1800242c9  cmp     [rsp+0AC0h+DestinationString.MaximumLength], ax
0x1800242ce  jnb     short loc_180024343
0x1800242d0  mov     rbx, [rsp+0AC0h+DestinationString.Buffer]
0x1800242d5  test    rbx, rbx
0x1800242d8  jz      short loc_180024300
0x1800242da  call    cs:__imp_GetProcessHeap
0x1800242e0  mov     rcx, rax; hHeap
0x1800242e3  mov     r8, rbx; lpMem
0x1800242e6  xor     edx, edx; dwFlags
0x1800242e8  call    cs:__imp_HeapFree
0x1800242ee  xor     edx, edx; SourceString
0x1800242f0  lea     rcx, [rsp+0AC0h+DestinationString]; DestinationString
0x1800242f5  call    cs:__imp_RtlInitUnicodeString
0x1800242fb  movzx   eax, [rsp+0AC0h+SourceString.Length]
0x180024300  movzx   ebx, ax
0x180024303  inc     ebx
0x180024305  add     rbx, rbx
0x180024308  call    cs:__imp_GetProcessHeap
0x18002430e  mov     rcx, rax; hHeap
0x180024311  mov     r8, rbx; dwBytes
0x180024314  mov     edx, 8; dwFlags
0x180024319  call    cs:__imp_HeapAlloc
0x18002431f  mov     [rsp+0AC0h+DestinationString.Buffer], rax
0x180024324  test    rax, rax
0x180024327  jz      loc_1800243D5
0x18002432d  movzx   eax, [rsp+0AC0h+SourceString.Length]
0x180024332  inc     ax
0x180024335  add     ax, ax
0x180024338  mov     [rsp+0AC0h+DestinationString.MaximumLength], ax
0x18002433d  mov     [rsp+0AC0h+DestinationString.Length], r15w
0x180024343  xor     r8d, r8d; AllocateDestinationString
0x180024346  lea     rdx, [rsp+0AC0h+SourceString]; SourceString
0x18002434b  lea     rcx, [rsp+0AC0h+DestinationString]; DestinationString
0x180024350  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180024356  test    eax, eax
0x180024358  jns     short loc_180024362
0x18002435a  mov     edi, eax
0x18002435c  bts     edi, 1Ch
0x180024360  jmp     short loc_180024374
0x180024362  movzx   edx, [rsp+0AC0h+DestinationString.Length]
0x180024367  shr     rdx, 1
0x18002436a  mov     rax, [rsp+0AC0h+DestinationString.Buffer]
0x18002436f  mov     [rax+rdx*2], r15w
0x180024374  test    edi, edi
0x180024376  jnz     short loc_1800243E7
0x180024378  lea     rcx, [rbp+9C0h+var_A40]
0x18002437c  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180024381  nop
0x180024382  lea     rdx, [rbp+9C0h+var_A40]
0x180024386  mov     rcx, [rsp+0AC0h+DestinationString.Buffer]
0x18002438b  call    ?ParseHost@@YAKPEAGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; ParseHost(ushort *,std::set<std::wstring> &)
0x180024390  test    eax, eax
0x180024392  jnz     short loc_1800243A9
0x180024394  lea     r8, [rbp+9C0h+var_A40]
0x180024398  mov     rdx, [rsp+0AC0h+var_A60.Buffer]
0x18002439d  mov     rcx, r13
0x1800243a0  call    ?EnumNetGroupCallBack@@YAKPEAXPEAGAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; EnumNetGroupCallBack(void *,ushort *,std::set<std::wstring> &)
0x1800243a5  mov     edi, eax
0x1800243a7  jmp     short loc_1800243BF
0x1800243a9  mov     rax, [r12]
0x1800243ad  mov     edx, 80001021h
0x1800243b2  mov     rcx, r12
0x1800243b5  mov     rax, [rax+8]
0x1800243b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243be  nop
0x1800243bf  lea     rcx, [rbp+9C0h+var_A40]
0x1800243c3  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x1800243c8  test    edi, edi
0x1800243ca  jnz     short loc_1800243E7
0x1800243cc  mov     rsi, [rsi+30h]
0x1800243d0  jmp     loc_180024216
0x1800243d5  mov     edi, 8
0x1800243da  jmp     short loc_1800243E7
0x1800243dc  mov     ecx, 57h ; 'W'
0x1800243e1  cmp     eax, 2
0x1800243e4  cmovnz  edi, ecx
0x1800243e7  lea     rcx, [rbp+9C0h+var_A30]
0x1800243eb  call    free_ypproc_all_2_result
0x1800243f0  mov     rax, [r14+8]
0x1800243f4  mov     rcx, r14
0x1800243f7  mov     rax, [rax+20h]
0x1800243fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024400  mov     eax, edi
0x180024402  mov     rcx, [rbp+9C0h+var_40]
0x180024409  xor     rcx, rsp; StackCookie
0x18002440c  call    __security_check_cookie
0x180024411  mov     rbx, [rsp+0AC0h+arg_0]
0x180024419  add     rsp, 0A90h
0x180024420  pop     r15
0x180024422  pop     r14
0x180024424  pop     r13
0x180024426  pop     r12
0x180024428  pop     rdi
0x180024429  pop     rsi
0x18002442a  pop     rbp
0x18002442b  retn
```
