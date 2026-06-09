# CDlgPropertyPolicy::OnRemoveUrl(uint,int,HWND__ *)

- ea: `0x180024bb8`
- end: `0x180024e1c`
- name: `?OnRemoveUrl@CDlgPropertyPolicy@@AEAAXIHPEAUHWND__@@@Z`
- size: `612`
- prototype: `void __fastcall(CDlgPropertyPolicy *__hidden this, unsigned int, int, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026460`

## callees

- `0x180014440`
- `0x180024050`
- `0x180024bb8`
- `0x1800256b8`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024ce0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024d3c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024ce0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024d3c`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180024d6f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180024d6f`
- `USER32!SendMessageA` at `0x180024beb`
- `USER32!SendMessageA` at `0x180024c03`
- `USER32!SendMessageA` at `0x180024c1b`
- `USER32!SendMessageA` at `0x180024cc3`
- `USER32!SendMessageA` at `0x180024d24`
- `USER32!SendMessageA` at `0x180024da1`
- `USER32!SendMessageA` at `0x180024beb`
- `USER32!SendMessageA` at `0x180024c03`
- `USER32!SendMessageA` at `0x180024c1b`
- `USER32!SendMessageA` at `0x180024cc3`
- `USER32!SendMessageA` at `0x180024d24`
- `USER32!SendMessageA` at `0x180024da1`
- `USER32!SetFocus` at `0x180024dfb`
- `USER32!SetFocus` at `0x180024dfb`
- `USER32!EnableWindow` at `0x180024dc3`
- `USER32!EnableWindow` at `0x180024dd2`
- `USER32!EnableWindow` at `0x180024dc3`
- `USER32!EnableWindow` at `0x180024dd2`

## pseudocode

```c
void __fastcall CDlgPropertyPolicy::OnRemoveUrl(HWND *this, __int64 a2, __int64 a3, HWND a4)
{
  int v5; // r12d
  int v6; // esi
  int v7; // edi
  int v8; // ebp
  const unsigned __int16 *v9; // rax
  const unsigned __int16 ***v10; // rcx
  int i; // esi
  _WORD *v12; // rax
  LPARAM v13; // r14
  HWND v14; // rcx
  _QWORD *v15; // rax
  HWND v16; // rcx
  int v17; // ebp
  __int64 v18; // r13
  _QWORD *v19; // rax
  HWND v20; // rcx
  LPARAM lParam[4]; // [rsp+30h] [rbp-98h] BYREF
  int v22; // [rsp+50h] [rbp-78h]
  int MaxUrlLength; // [rsp+E0h] [rbp+18h]
  HWND v24; // [rsp+E8h] [rbp+20h] BYREF

  v24 = a4;
  v5 = SendMessageA(this[10], 0x1032u, 0, 0);
  v6 = SendMessageA(this[10], 0x1042u, 0, 0);
  v7 = SendMessageA(this[10], 0x1004u, 0, 0);
  MaxUrlLength = CDlgPropertyPolicy::GetMaxUrlLength((CDlgPropertyPolicy *)this);
  v8 = MaxUrlLength;
  if ( v6 >= 0 && v6 < v7 )
  {
    if ( *((_DWORD *)this + 62) || v5 != v7 )
    {
      for ( i = v7 - 1; i >= 0; --i )
      {
        if ( (unsigned int)SendMessageA(this[10], 0x102Cu, i, 2) == 2 )
        {
          v12 = LocalAlloc(0x40u, 2LL * v8 + 2);
          v13 = (LPARAM)v12;
          if ( !v12 )
            return;
          *v12 = 0;
          memset_0(lParam, 0, 0x58u);
          lParam[3] = v13;
          v22 = v8 + 1;
          SendMessageA(this[10], 0x1073u, i, (LPARAM)lParam);
          v14 = this[29];
          if ( v14 )
          {
            v18 = *((unsigned int *)this + 60);
            v17 = v18 + 1;
            v19 = LocalReAlloc(v14, 8LL * (unsigned int)(v18 + 1), 2u);
            v16 = (HWND)v19;
            if ( !v19 )
              return;
            v19[v18] = v13;
          }
          else
          {
            v15 = LocalAlloc(0x40u, 8u);
            v16 = (HWND)v15;
            if ( !v15 )
              return;
            *v15 = v13;
            v17 = 1;
          }
          this[29] = v16;
          *((_DWORD *)this + 60) = v17;
          SendMessageA(this[10], 0x1008u, i, 0);
          v8 = MaxUrlLength;
        }
      }
      if ( v5 == v7 )
      {
        EnableWindow(this[21], 0);
        EnableWindow(this[22], 0);
        v20 = *(HWND *)ATL::CWindow::GetDlgItem(this + 1, &v24, 1);
      }
      else
      {
        v20 = this[23];
      }
      SetFocus(v20);
    }
    else
    {
      v9 = (const unsigned __int16 *)this[25];
      if ( !v9 )
      {
        if ( this[24] )
        {
          v9 = (const unsigned __int16 *)this[24];
        }
        else
        {
          v10 = (const unsigned __int16 ***)this[27];
          if ( v10 )
            v9 = **v10;
        }
      }
      CDlgPropertyPolicy::ShowRemoveMessageBox((CDlgPropertyPolicy *)this, 0xD71u, 0xD70u, 0x30u, v9);
    }
  }
}

```

## disassembly

```asm
0x180024bb8  mov     [rsp+arg_0], rbx
0x180024bbd  mov     [rsp+arg_18], r9
0x180024bc2  mov     [rsp+arg_10], r8d
0x180024bc7  push    rbp
0x180024bc8  push    rsi
0x180024bc9  push    rdi
0x180024bca  push    r12
0x180024bcc  push    r13
0x180024bce  push    r14
0x180024bd0  push    r15
0x180024bd2  sub     rsp, 90h
0x180024bd9  mov     rbx, rcx
0x180024bdc  xor     r9d, r9d; lParam
0x180024bdf  mov     rcx, [rcx+50h]; hWnd
0x180024be3  xor     r8d, r8d; wParam
0x180024be6  mov     edx, 1032h; Msg
0x180024beb  call    cs:__imp_SendMessageA
0x180024bf1  mov     rcx, [rbx+50h]; hWnd
0x180024bf5  xor     r9d, r9d; lParam
0x180024bf8  xor     r8d, r8d; wParam
0x180024bfb  mov     edx, 1042h; Msg
0x180024c00  mov     r12, rax
0x180024c03  call    cs:__imp_SendMessageA
0x180024c09  mov     rcx, [rbx+50h]; hWnd
0x180024c0d  xor     r9d, r9d; lParam
0x180024c10  xor     r8d, r8d; wParam
0x180024c13  mov     edx, 1004h; Msg
0x180024c18  mov     rsi, rax
0x180024c1b  call    cs:__imp_SendMessageA
0x180024c21  mov     rcx, rbx; this
0x180024c24  mov     rdi, rax
0x180024c27  call    ?GetMaxUrlLength@CDlgPropertyPolicy@@AEAAHXZ; CDlgPropertyPolicy::GetMaxUrlLength(void)
0x180024c2c  mov     [rsp+0C8h+arg_10], eax
0x180024c33  mov     ebp, eax
0x180024c35  test    esi, esi
0x180024c37  js      loc_180024E01
0x180024c3d  cmp     esi, edi
0x180024c3f  jge     loc_180024E01
0x180024c45  cmp     dword ptr [rbx+0F8h], 0
0x180024c4c  jnz     short loc_180024CA3
0x180024c4e  cmp     r12d, edi
0x180024c51  jnz     short loc_180024CA3
0x180024c53  mov     rax, [rbx+0C8h]
0x180024c5a  test    rax, rax
0x180024c5d  jnz     short loc_180024C82
0x180024c5f  mov     rcx, [rbx+0C0h]
0x180024c66  test    rcx, rcx
0x180024c69  jz      short loc_180024C70
0x180024c6b  mov     rax, rcx
0x180024c6e  jmp     short loc_180024C82
0x180024c70  mov     rcx, [rbx+0D8h]
0x180024c77  test    rcx, rcx
0x180024c7a  jz      short loc_180024C82
0x180024c7c  mov     rax, [rcx]
0x180024c7f  mov     rax, [rax]
0x180024c82  mov     edx, 0D71h; unsigned int
0x180024c87  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 *
0x180024c8c  mov     r9d, 30h ; '0'; unsigned int
0x180024c92  mov     rcx, rbx; this
0x180024c95  lea     r8d, [rdx-1]; unsigned int
0x180024c99  call    ?ShowRemoveMessageBox@CDlgPropertyPolicy@@AEAAHIIIPEBG@Z; CDlgPropertyPolicy::ShowRemoveMessageBox(uint,uint,uint,ushort const *)
0x180024c9e  jmp     loc_180024E01
0x180024ca3  lea     esi, [rdi-1]
0x180024ca6  test    esi, esi
0x180024ca8  js      loc_180024DB5
0x180024cae  mov     rcx, [rbx+50h]; hWnd
0x180024cb2  mov     r9d, 2; lParam
0x180024cb8  movsxd  r15, esi
0x180024cbb  mov     edx, 102Ch; Msg
0x180024cc0  mov     r8, r15; wParam
0x180024cc3  call    cs:__imp_SendMessageA
0x180024cc9  cmp     eax, 2
0x180024ccc  jnz     loc_180024DAE
0x180024cd2  movsxd  rdx, ebp
0x180024cd5  lea     ecx, [rax+3Eh]; uFlags
0x180024cd8  lea     rdx, ds:2[rdx*2]; uBytes
0x180024ce0  call    cs:__imp_LocalAlloc
0x180024ce6  mov     r14, rax
0x180024ce9  test    rax, rax
0x180024cec  jz      loc_180024E01
0x180024cf2  xor     ecx, ecx
0x180024cf4  xor     edx, edx; Val
0x180024cf6  mov     [rax], cx
0x180024cf9  lea     r8d, [rcx+58h]; Size
0x180024cfd  lea     rcx, [rsp+0C8h+lParam]; void *
0x180024d02  call    memset_0
0x180024d07  lea     ecx, [rbp+1]
0x180024d0a  mov     [rsp+0C8h+var_80], r14
0x180024d0f  mov     [rsp+0C8h+var_78], ecx
0x180024d13  lea     r9, [rsp+0C8h+lParam]; lParam
0x180024d18  mov     rcx, [rbx+50h]; hWnd
0x180024d1c  mov     r8, r15; wParam
0x180024d1f  mov     edx, 1073h; Msg
0x180024d24  call    cs:__imp_SendMessageA
0x180024d2a  mov     rcx, [rbx+0E8h]; hMem
0x180024d31  test    rcx, rcx
0x180024d34  jnz     short loc_180024D58
0x180024d36  lea     edx, [rcx+8]; uBytes
0x180024d39  lea     ecx, [rdx+38h]; uFlags
0x180024d3c  call    cs:__imp_LocalAlloc
0x180024d42  mov     rcx, rax
0x180024d45  test    rax, rax
0x180024d48  jz      loc_180024E01
0x180024d4e  mov     [rax], r14
0x180024d51  mov     ebp, 1
0x180024d56  jmp     short loc_180024D85
0x180024d58  mov     r13d, [rbx+0F0h]
0x180024d5f  mov     r8d, 2; uFlags
0x180024d65  lea     ebp, [r13+1]
0x180024d69  mov     edx, ebp
0x180024d6b  shl     rdx, 3; uBytes
0x180024d6f  call    cs:__imp_LocalReAlloc
0x180024d75  mov     rcx, rax
0x180024d78  test    rax, rax
0x180024d7b  jz      loc_180024E01
0x180024d81  mov     [rax+r13*8], r14
0x180024d85  mov     [rbx+0E8h], rcx
0x180024d8c  mov     [rbx+0F0h], ebp
0x180024d92  mov     rcx, [rbx+50h]; hWnd
0x180024d96  xor     r9d, r9d; lParam
0x180024d99  mov     r8, r15; wParam
0x180024d9c  mov     edx, 1008h; Msg
0x180024da1  call    cs:__imp_SendMessageA
0x180024da7  mov     ebp, [rsp+0C8h+arg_10]
0x180024dae  dec     esi
0x180024db0  jmp     loc_180024CA6
0x180024db5  cmp     r12d, edi
0x180024db8  jnz     short loc_180024DF4
0x180024dba  mov     rcx, [rbx+0A8h]; hWnd
0x180024dc1  xor     edx, edx; bEnable
0x180024dc3  call    cs:__imp_EnableWindow
0x180024dc9  mov     rcx, [rbx+0B0h]; hWnd
0x180024dd0  xor     edx, edx; bEnable
0x180024dd2  call    cs:__imp_EnableWindow
0x180024dd8  lea     rcx, [rbx+8]
0x180024ddc  mov     r8d, 1
0x180024de2  lea     rdx, [rsp+0C8h+arg_18]
0x180024dea  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024def  mov     rcx, [rax]
0x180024df2  jmp     short loc_180024DFB
0x180024df4  mov     rcx, [rbx+0B8h]; hWnd
0x180024dfb  call    cs:__imp_SetFocus
0x180024e01  mov     rbx, [rsp+0C8h+arg_0]
0x180024e09  add     rsp, 90h
0x180024e10  pop     r15
0x180024e12  pop     r14
0x180024e14  pop     r13
0x180024e16  pop     r12
0x180024e18  pop     rdi
0x180024e19  pop     rsi
0x180024e1a  pop     rbp
0x180024e1b  retn
```
