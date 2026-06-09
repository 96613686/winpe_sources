# NhCreateStreamSocket(sockaddr_storage *,_NH_RCSOCKET *)

- ea: `0x180055fc0`
- end: `0x1800562f5`
- name: `?NhCreateStreamSocket@@YAKPEAUsockaddr_storage@@PEAU_NH_RCSOCKET@@@Z`
- size: `821`
- prototype: `unsigned int __fastcall(struct sockaddr_storage *, struct _NH_RCSOCKET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180055870`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180055fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056042`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005625a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005625a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180056108`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180056108`
- `WS2_32!WSASocketW` at `0x1800560bb`
- `WS2_32!WSASocketW` at `0x1800560bb`
- `WS2_32!__imp_bind` at `0x1800561f6`
- `WS2_32!__imp_bind` at `0x1800561f6`
- `WS2_32!__imp_closesocket` at `0x18005623f`
- `WS2_32!__imp_closesocket` at `0x18005623f`
- `WS2_32!__imp_setsockopt` at `0x18005616c`
- `WS2_32!__imp_setsockopt` at `0x180056190`
- `WS2_32!__imp_setsockopt` at `0x18005616c`
- `WS2_32!__imp_setsockopt` at `0x180056190`
- `WS2_32!__imp_WSAGetLastError` at `0x1800560ca`
- `WS2_32!__imp_WSAGetLastError` at `0x180056205`
- `WS2_32!__imp_WSAGetLastError` at `0x1800560ca`
- `WS2_32!__imp_WSAGetLastError` at `0x180056205`

## pseudocode

```c
__int64 __fastcall NhCreateStreamSocket(struct sockaddr_storage *a1, struct _NH_RCSOCKET *a2)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  DWORD v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rax
  SOCKET v10; // rsi
  DWORD Error; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  char optval[16]; // [rsp+30h] [rbp-69h] BYREF
  struct sockaddr name; // [rsp+40h] [rbp-59h] BYREF
  __int128 v25; // [rsp+50h] [rbp-49h]
  __int128 v26; // [rsp+60h] [rbp-39h]
  __int128 v27; // [rsp+70h] [rbp-29h]
  __int128 v28; // [rsp+80h] [rbp-19h]
  __int128 v29; // [rsp+90h] [rbp-9h]
  __int128 v30; // [rsp+A0h] [rbp+7h]
  __int128 v31; // [rsp+B0h] [rbp+17h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  *(_DWORD *)optval = 0;
  memset_0(&name, 0, 0x80u);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a2 + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v8 = 47;
    goto LABEL_10;
  }
  *(_DWORD *)a2 = 2;
  v9 = (void *)WSASocketW(2, 1, 6, 0, 0, 1u);
  v10 = (SOCKET)v9;
  if ( v9 == (void *)-1LL )
  {
    LastError = WSAGetLastError();
    v6 = LastError;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v8 = 48;
LABEL_10:
    WPP_SF_d(v7[2], v8, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
LABEL_31:
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_32:
    if ( *((_QWORD *)a2 + 1) )
    {
      _InterlockedDecrement((volatile signed __int32 *)a2);
      CloseHandle(*((HANDLE *)a2 + 1));
      *((_QWORD *)a2 + 1) = 0;
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      WPP_SF_d(v7[2], 52, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v6);
    return v6;
  }
  if ( !BindIoCompletionCallback(v9, NhpIoCompletionRoutine, 0) )
  {
    Error = GetLastError();
    v6 = Error;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_30;
    }
    v13 = 49;
LABEL_29:
    WPP_SF_d(v12[2], v13, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, Error);
LABEL_30:
    closesocket(v10);
    goto LABEL_31;
  }
  *(_DWORD *)optval = 0;
  setsockopt(v10, 0xFFFF, 4097, optval, 4);
  *(_DWORD *)optval = 0;
  setsockopt(v10, 0xFFFF, 4098, optval, 4);
  v14 = 8;
  if ( a1->ss_family != 23 )
    v14 = 4;
  if ( *(_DWORD *)((char *)&a1->ss_family + v14) != -1 )
  {
    v15 = *(_OWORD *)a1->__ss_pad2;
    name = *(struct sockaddr *)&a1->ss_family;
    v16 = *(_OWORD *)&a1->__ss_pad2[16];
    v25 = v15;
    v17 = *(_OWORD *)&a1->__ss_pad2[32];
    v26 = v16;
    v18 = *(_OWORD *)&a1->__ss_pad2[48];
    v27 = v17;
    v19 = *(_OWORD *)&a1->__ss_pad2[64];
    v28 = v18;
    v20 = *(_OWORD *)&a1->__ss_pad2[80];
    v29 = v19;
    v21 = *(_OWORD *)&a1->__ss_pad2[96];
    v30 = v20;
    v31 = v21;
    if ( bind(v10, &name, 128) == -1 )
    {
      Error = WSAGetLastError();
      v6 = Error;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v13 = 50;
      goto LABEL_29;
    }
  }
  *((_QWORD *)a2 + 2) = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180055fc0  mov     [rsp-8+arg_10], rbx
0x180055fc5  push    rbp
0x180055fc6  push    rsi
0x180055fc7  push    rdi
0x180055fc8  push    r13
0x180055fca  push    r15
0x180055fcc  lea     rbp, [rsp-37h]
0x180055fd1  sub     rsp, 0D0h
0x180055fd8  mov     rax, cs:__security_cookie
0x180055fdf  xor     rax, rsp
0x180055fe2  mov     [rbp+57h+var_30], rax
0x180055fe6  mov     rdi, rdx
0x180055fe9  mov     rbx, rcx
0x180055fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ff3  lea     r13, WPP_GLOBAL_Control
0x180055ffa  cmp     rcx, r13
0x180055ffd  jz      short loc_180056020
0x180055fff  test    byte ptr [rcx+1Ch], 8
0x180056003  jz      short loc_180056020
0x180056005  cmp     byte ptr [rcx+19h], 6
0x180056009  jb      short loc_180056020
0x18005600b  mov     rcx, [rcx+10h]
0x18005600f  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x180056016  mov     edx, 2Eh ; '.'
0x18005601b  call    WPP_SF_
0x180056020  xor     edx, edx; Val
0x180056022  mov     dword ptr [rbp+57h+optval], 0
0x180056029  mov     r8d, 80h; Size
0x18005602f  lea     rcx, [rbp+57h+name]; void *
0x180056033  call    memset_0
0x180056038  xor     r9d, r9d; lpName
0x18005603b  xor     r8d, r8d; bInitialState
0x18005603e  xor     edx, edx; bManualReset
0x180056040  xor     ecx, ecx; lpEventAttributes
0x180056042  call    cs:__imp_CreateEventW
0x180056048  mov     [rdi+8], rax
0x18005604c  test    rax, rax
0x18005604f  jnz     short loc_18005609A
0x180056051  call    cs:__imp_GetLastError
0x180056057  mov     ebx, eax
0x180056059  mov     rcx, cs:WPP_GLOBAL_Control
0x180056060  cmp     rcx, r13
0x180056063  jz      loc_18005624C
0x180056069  test    byte ptr [rcx+1Ch], 8
0x18005606d  jz      loc_18005624C
0x180056073  cmp     byte ptr [rcx+19h], 2
0x180056077  jb      loc_18005624C
0x18005607d  mov     edx, 2Fh ; '/'
0x180056082  mov     rcx, [rcx+10h]
0x180056086  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005608d  mov     r9d, eax
0x180056090  call    WPP_SF_d
0x180056095  jmp     loc_180056245
0x18005609a  mov     edx, 1; type
0x18005609f  mov     dword ptr [rdi], 2
0x1800560a5  mov     [rsp+0F0h+dwFlags], edx; dwFlags
0x1800560a9  xor     r9d, r9d; lpProtocolInfo
0x1800560ac  mov     [rsp+0F0h+g], 0; g
0x1800560b4  lea     ecx, [rdx+1]; af
0x1800560b7  lea     r8d, [rdx+5]; protocol
0x1800560bb  call    cs:__imp_WSASocketW
0x1800560c1  mov     rsi, rax
0x1800560c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800560c8  jnz     short loc_1800560FB
0x1800560ca  call    cs:__imp_WSAGetLastError
0x1800560d0  mov     ebx, eax
0x1800560d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560d9  cmp     rcx, r13
0x1800560dc  jz      loc_18005624C
0x1800560e2  test    byte ptr [rcx+1Ch], 8
0x1800560e6  jz      loc_18005624C
0x1800560ec  cmp     byte ptr [rcx+19h], 2
0x1800560f0  jb      loc_18005624C
0x1800560f6  lea     edx, [rsi+31h]
0x1800560f9  jmp     short loc_180056082
0x1800560fb  xor     r8d, r8d; Flags
0x1800560fe  lea     rdx, ?NhpIoCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x180056105  mov     rcx, rsi; FileHandle
0x180056108  call    cs:__imp_BindIoCompletionCallback
0x18005610e  test    eax, eax
0x180056110  jnz     short loc_180056148
0x180056112  call    cs:__imp_GetLastError
0x180056118  mov     ebx, eax
0x18005611a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056121  cmp     rcx, r13
0x180056124  jz      loc_18005623C
0x18005612a  test    byte ptr [rcx+1Ch], 8
0x18005612e  jz      loc_18005623C
0x180056134  cmp     byte ptr [rcx+19h], 2
0x180056138  jb      loc_18005623C
0x18005613e  mov     edx, 31h ; '1'
0x180056143  jmp     loc_180056229
0x180056148  mov     r15d, 4
0x18005614e  mov     dword ptr [rbp+57h+optval], 0
0x180056155  lea     r9, [rbp+57h+optval]; optval
0x180056159  mov     [rsp+0F0h+g], r15d; optlen
0x18005615e  mov     edx, 0FFFFh; level
0x180056163  mov     r8d, 1001h; optname
0x180056169  mov     rcx, rsi; s
0x18005616c  call    cs:__imp_setsockopt
0x180056172  lea     r9, [rbp+57h+optval]; optval
0x180056176  mov     dword ptr [rbp+57h+optval], 0
0x18005617d  mov     edx, 0FFFFh; level
0x180056182  mov     [rsp+0F0h+g], r15d; optlen
0x180056187  mov     r8d, 1002h; optname
0x18005618d  mov     rcx, rsi; s
0x180056190  call    cs:__imp_setsockopt
0x180056196  cmp     word ptr [rbx], 17h
0x18005619a  lea     eax, [r15+4]
0x18005619e  cmovnz  eax, r15d
0x1800561a2  cmp     dword ptr [rax+rbx], 0FFFFFFFFh
0x1800561a6  jz      loc_18005629C
0x1800561ac  movups  xmm0, xmmword ptr [rbx]
0x1800561af  lea     r8d, [r15+7Ch]; namelen
0x1800561b3  mov     rcx, rsi; s
0x1800561b6  movups  xmm1, xmmword ptr [rbx+10h]
0x1800561ba  lea     rdx, [rbp+57h+name]; name
0x1800561be  movaps  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x1800561c2  movups  xmm0, xmmword ptr [rbx+20h]
0x1800561c6  movaps  [rbp+57h+var_A0], xmm1
0x1800561ca  movups  xmm1, xmmword ptr [rbx+30h]
0x1800561ce  movaps  [rbp+57h+var_90], xmm0
0x1800561d2  movups  xmm0, xmmword ptr [rbx+40h]
0x1800561d6  movaps  [rbp+57h+var_80], xmm1
0x1800561da  movups  xmm1, xmmword ptr [rbx+50h]
0x1800561de  movaps  [rbp+57h+var_70], xmm0
0x1800561e2  movups  xmm0, xmmword ptr [rbx+60h]
0x1800561e6  movaps  [rbp+57h+var_60], xmm1
0x1800561ea  movups  xmm1, xmmword ptr [rbx+70h]
0x1800561ee  movaps  [rbp+57h+var_50], xmm0
0x1800561f2  movaps  [rbp+57h+var_40], xmm1
0x1800561f6  call    cs:__imp_bind
0x1800561fc  cmp     eax, 0FFFFFFFFh
0x1800561ff  jnz     loc_18005629C
0x180056205  call    cs:__imp_WSAGetLastError
0x18005620b  mov     ebx, eax
0x18005620d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056214  cmp     rcx, r13
0x180056217  jz      short loc_18005623C
0x180056219  test    byte ptr [rcx+1Ch], 8
0x18005621d  jz      short loc_18005623C
0x18005621f  cmp     byte ptr [rcx+19h], 2
0x180056223  jb      short loc_18005623C
0x180056225  lea     edx, [r15+2Eh]
0x180056229  mov     rcx, [rcx+10h]
0x18005622d  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x180056234  mov     r9d, eax
0x180056237  call    WPP_SF_d
0x18005623c  mov     rcx, rsi; s
0x18005623f  call    cs:__imp_closesocket
0x180056245  mov     rcx, cs:WPP_GLOBAL_Control
0x18005624c  cmp     qword ptr [rdi+8], 0
0x180056251  jz      short loc_18005626F
0x180056253  lock dec dword ptr [rdi]
0x180056256  mov     rcx, [rdi+8]; hObject
0x18005625a  call    cs:__imp_CloseHandle
0x180056260  mov     qword ptr [rdi+8], 0
0x180056268  mov     rcx, cs:WPP_GLOBAL_Control
0x18005626f  cmp     rcx, r13
0x180056272  jz      short loc_180056298
0x180056274  test    byte ptr [rcx+1Ch], 8
0x180056278  jz      short loc_180056298
0x18005627a  cmp     byte ptr [rcx+19h], 6
0x18005627e  jb      short loc_180056298
0x180056280  mov     rcx, [rcx+10h]
0x180056284  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005628b  mov     edx, 34h ; '4'
0x180056290  mov     r9d, ebx
0x180056293  call    WPP_SF_d
0x180056298  mov     eax, ebx
0x18005629a  jmp     short loc_1800562D2
0x18005629c  mov     [rdi+10h], rsi
0x1800562a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562a7  cmp     rcx, r13
0x1800562aa  jz      short loc_1800562D0
0x1800562ac  test    byte ptr [rcx+1Ch], 8
0x1800562b0  jz      short loc_1800562D0
0x1800562b2  cmp     byte ptr [rcx+19h], 6
0x1800562b6  jb      short loc_1800562D0
0x1800562b8  mov     rcx, [rcx+10h]
0x1800562bc  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x1800562c3  mov     edx, 33h ; '3'
0x1800562c8  xor     r9d, r9d
0x1800562cb  call    WPP_SF_d
0x1800562d0  xor     eax, eax
0x1800562d2  mov     rcx, [rbp+57h+var_30]
0x1800562d6  xor     rcx, rsp; StackCookie
0x1800562d9  call    __security_check_cookie
0x1800562de  mov     rbx, [rsp+0F0h+arg_10]
0x1800562e6  add     rsp, 0D0h
0x1800562ed  pop     r15
0x1800562ef  pop     r13
0x1800562f1  pop     rdi
0x1800562f2  pop     rsi
0x1800562f3  pop     rbp
0x1800562f4  retn
```
