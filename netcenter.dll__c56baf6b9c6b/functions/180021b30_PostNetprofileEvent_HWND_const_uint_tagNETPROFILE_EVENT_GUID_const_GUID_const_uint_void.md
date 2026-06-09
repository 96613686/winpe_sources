# PostNetprofileEvent(HWND__ * const,uint,tagNETPROFILE_EVENT,_GUID const *,_GUID const *,uint,void *)

- ea: `0x180021b30`
- end: `0x180021bf4`
- name: `?PostNetprofileEvent@@YAJQEAUHWND__@@IW4tagNETPROFILE_EVENT@@PEBU_GUID@@2IPEAX@Z`
- size: `196`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e150`
- `0x18000e190`
- `0x18000e1d0`
- `0x18000e210`
- `0x18000e250`
- `0x18000e3e0`
- `0x18000e420`
- `0x18000e460`
- `0x18000e4a0`
- `0x18000e4e0`
- `0x18000e520`

## callees

- `0x180014274`
- `0x180021b30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021b4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021b4b`
- `USER32!PostMessageW` at `0x180021ba9`
- `USER32!PostMessageW` at `0x180021ba9`

## pseudocode

```c
__int64 __fastcall PostNetprofileEvent(HWND a1, __int64 a2, int a3, _OWORD *a4, _OWORD *a5, int a6, __int64 a7)
{
  __int64 v8; // rdi
  _BYTE *v11; // rax
  LPARAM v12; // r9
  unsigned int v13; // ebx

  v8 = 48;
  v11 = CoTaskMemAlloc(0x30u);
  v12 = (LPARAM)v11;
  if ( v11 )
  {
    v13 = 0;
    do
    {
      *v11++ = 0;
      --v8;
    }
    while ( v8 );
    *(_DWORD *)(v12 + 36) = a6;
    *(_QWORD *)(v12 + 40) = a7;
    *(_DWORD *)v12 = a3;
    if ( a4 )
      *(_OWORD *)(v12 + 4) = *a4;
    if ( a5 )
      *(_OWORD *)(v12 + 20) = *a5;
    PostMessageW(a1, 0x8003u, 0, v12);
  }
  else
  {
    v13 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6d1483d85eae3b79824b7b2fc4220657_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180021b30  push    rbx
0x180021b32  push    rbp
0x180021b33  push    rsi
0x180021b34  push    rdi
0x180021b35  push    r14
0x180021b37  sub     rsp, 20h
0x180021b3b  mov     r14, rcx
0x180021b3e  mov     edi, 30h ; '0'
0x180021b43  mov     ecx, edi; cb
0x180021b45  mov     rsi, r9
0x180021b48  mov     ebp, r8d
0x180021b4b  call    cs:__imp_CoTaskMemAlloc
0x180021b51  mov     r9, rax; lParam
0x180021b54  test    rax, rax
0x180021b57  jz      short loc_180021BB1
0x180021b59  xor     ebx, ebx
0x180021b5b  mov     [rax], bl
0x180021b5d  inc     rax
0x180021b60  sub     rdi, 1
0x180021b64  jnz     short loc_180021B5B
0x180021b66  mov     eax, [rsp+48h+arg_28]
0x180021b6a  mov     [r9+24h], eax
0x180021b6e  mov     rax, [rsp+48h+arg_30]
0x180021b76  mov     [r9+28h], rax
0x180021b7a  mov     [r9], ebp
0x180021b7d  test    rsi, rsi
0x180021b80  jz      short loc_180021B8B
0x180021b82  movups  xmm0, xmmword ptr [rsi]
0x180021b85  movdqu  xmmword ptr [r9+4], xmm0
0x180021b8b  mov     rax, [rsp+48h+arg_20]
0x180021b90  test    rax, rax
0x180021b93  jz      short loc_180021B9E
0x180021b95  movups  xmm0, xmmword ptr [rax]
0x180021b98  movdqu  xmmword ptr [r9+14h], xmm0
0x180021b9e  xor     r8d, r8d; wParam
0x180021ba1  mov     edx, 8003h; Msg
0x180021ba6  mov     rcx, r14; hWnd
0x180021ba9  call    cs:__imp_PostMessageW
0x180021baf  jmp     short loc_180021BB6
0x180021bb1  mov     ebx, 8007000Eh
0x180021bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bbd  lea     rax, WPP_GLOBAL_Control
0x180021bc4  cmp     rcx, rax
0x180021bc7  jz      short loc_180021BE7
0x180021bc9  test    byte ptr [rcx+1Ch], 8
0x180021bcd  jz      short loc_180021BE7
0x180021bcf  mov     rcx, [rcx+10h]
0x180021bd3  lea     r8, WPP_6d1483d85eae3b79824b7b2fc4220657_Traceguids
0x180021bda  mov     edx, 0Ah
0x180021bdf  mov     r9d, ebx
0x180021be2  call    WPP_SF_d
0x180021be7  mov     eax, ebx
0x180021be9  add     rsp, 20h
0x180021bed  pop     r14
0x180021bef  pop     rdi
0x180021bf0  pop     rsi
0x180021bf1  pop     rbp
0x180021bf2  pop     rbx
0x180021bf3  retn
```
