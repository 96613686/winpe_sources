# CFaxCommon::SendMessageToFirstWFSInstance(int,ushort const *,uint,unsigned __int64,__int64,ushort const *)

- ea: `0x180004fc0`
- end: `0x18000505f`
- name: `?SendMessageToFirstWFSInstance@CFaxCommon@@UEAAJHPEBGI_K_J0@Z`
- size: `159`
- prototype: `__int64 __fastcall(CFaxCommon *this, int, const unsigned __int16 *, UINT, WPARAM wParam, LPARAM lParam, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004fc0`

## import_xrefs

- `USER32!PostMessageW` at `0x18000504c`
- `USER32!PostMessageW` at `0x18000504c`
- `USER32!SendMessageW` at `0x180005044`
- `USER32!SendMessageW` at `0x180005044`
- `USER32!FindWindowW` at `0x180004fd4`
- `USER32!FindWindowW` at `0x180004fd4`

## pseudocode

```c
__int64 __fastcall CFaxCommon::SendMessageToFirstWFSInstance(
        CFaxCommon *this,
        int a2,
        const unsigned __int16 *a3,
        UINT a4,
        WPARAM wParam,
        LPARAM lParam,
        const unsigned __int16 *a7)
{
  HWND WindowW; // r10
  __int64 v10; // rax
  WPARAM v11; // r8
  __int128 *v12; // r9
  __int128 v14; // [rsp+20h] [rbp-28h] BYREF
  const unsigned __int16 *v15; // [rsp+30h] [rbp-18h]

  WindowW = FindWindowW(a3, 0);
  if ( WindowW )
  {
    v15 = 0;
    v14 = 0;
    if ( a4 == 74 )
    {
      v10 = -1;
      *(_QWORD *)&v14 = wParam;
      v15 = a7;
      do
        ++v10;
      while ( a7[v10] );
      v11 = 0;
      DWORD2(v14) = 2 * v10 + 2;
      v12 = &v14;
    }
    else
    {
      v12 = (__int128 *)lParam;
      v11 = wParam;
    }
    if ( a2 )
      SendMessageW(WindowW, a4, v11, (LPARAM)v12);
    else
      PostMessageW(WindowW, a4, v11, (LPARAM)v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180004fc0  mov     [rsp+arg_0], rbx
0x180004fc5  push    rdi
0x180004fc6  sub     rsp, 40h
0x180004fca  mov     edi, edx
0x180004fcc  mov     rcx, r8; lpClassName
0x180004fcf  xor     edx, edx; lpWindowName
0x180004fd1  mov     ebx, r9d
0x180004fd4  call    cs:__imp_FindWindowW
0x180004fda  xor     edx, edx
0x180004fdc  mov     r10, rax
0x180004fdf  test    rax, rax
0x180004fe2  jz      short loc_180005052
0x180004fe4  xor     eax, eax
0x180004fe6  xorps   xmm0, xmm0
0x180004fe9  mov     [rsp+48h+var_18], rax
0x180004fee  movups  [rsp+48h+var_28], xmm0
0x180004ff3  cmp     ebx, 4Ah ; 'J'
0x180004ff6  jnz     short loc_180005031
0x180004ff8  mov     rcx, [rsp+48h+wParam]
0x180004ffd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005001  mov     qword ptr [rsp+48h+var_28], rcx
0x180005006  mov     rcx, [rsp+48h+arg_30]
0x18000500e  mov     [rsp+48h+var_18], rcx
0x180005013  inc     rax
0x180005016  cmp     [rcx+rax*2], dx
0x18000501a  jnz     short loc_180005013
0x18000501c  lea     eax, ds:2[rax*2]
0x180005023  mov     r8, rdx
0x180005026  mov     dword ptr [rsp+48h+var_28+8], eax
0x18000502a  lea     r9, [rsp+48h+var_28]
0x18000502f  jmp     short loc_18000503B
0x180005031  mov     r9, [rsp+48h+lParam]; lParam
0x180005036  mov     r8, [rsp+48h+wParam]; wParam
0x18000503b  mov     edx, ebx; Msg
0x18000503d  mov     rcx, r10; hWnd
0x180005040  test    edi, edi
0x180005042  jz      short loc_18000504C
0x180005044  call    cs:__imp_SendMessageW
0x18000504a  jmp     short loc_180005052
0x18000504c  call    cs:__imp_PostMessageW
0x180005052  mov     rbx, [rsp+48h+arg_0]
0x180005057  xor     eax, eax
0x180005059  add     rsp, 40h
0x18000505d  pop     rdi
0x18000505e  retn
```
