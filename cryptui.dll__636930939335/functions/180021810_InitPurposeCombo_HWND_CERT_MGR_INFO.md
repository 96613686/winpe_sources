# InitPurposeCombo(HWND__ *,_CERT_MGR_INFO *)

- ea: `0x180021810`
- end: `0x1800219ec`
- name: `?InitPurposeCombo@@YAXPEAUHWND__@@PEAU_CERT_MGR_INFO@@@Z`
- size: `476`
- prototype: `void __fastcall(HWND hDlg, struct _CERT_MGR_INFO *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fda0`
- `0x180022178`

## callees

- `0x180021810`
- `0x18003e5c0`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800218d2`
- `msvcrt!_stricmp` at `0x1800218d2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021918`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021976`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021918`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021976`
- `USER32!SendDlgItemMessageA` at `0x180021882`
- `USER32!SendDlgItemMessageA` at `0x180021882`
- `USER32!SendDlgItemMessageW` at `0x1800218ba`
- `USER32!SendDlgItemMessageW` at `0x180021939`
- `USER32!SendDlgItemMessageW` at `0x180021999`
- `USER32!SendDlgItemMessageW` at `0x1800219bb`
- `USER32!SendDlgItemMessageW` at `0x1800218ba`
- `USER32!SendDlgItemMessageW` at `0x180021939`
- `USER32!SendDlgItemMessageW` at `0x180021999`
- `USER32!SendDlgItemMessageW` at `0x1800219bb`

## pseudocode

```c
void __fastcall InitPurposeCombo(HWND hDlg, struct _CERT_MGR_INFO *a2)
{
  __int64 v4; // r13
  WCHAR *lParam; // rbx
  __int64 i; // r14
  __int64 v7; // rax
  const char *v8; // rcx
  __int64 j; // rdi
  UINT v10; // edx
  UINT v11; // edx
  int v12; // eax
  UINT uID[4]; // [rsp+30h] [rbp-D0h]
  WCHAR Buffer[512]; // [rsp+40h] [rbp-C0h] BYREF

  if ( hDlg )
  {
    uID[0] = 6358;
    uID[1] = 6364;
    if ( a2 )
    {
      v4 = *(_QWORD *)a2;
      lParam = 0;
      SendDlgItemMessageA(hDlg, 1112, 0x14Bu, 0, 0);
      for ( i = 0; (unsigned int)i < *((_DWORD *)a2 + 6); i = (unsigned int)(i + 1) )
      {
        v7 = *((_QWORD *)a2 + 4);
        if ( !*(_DWORD *)(v7 + 24 * i + 8) )
        {
          SendDlgItemMessageW(hDlg, 1112, 0x143u, 0, *(_QWORD *)(v7 + 24 * i));
          v8 = *(const char **)(v4 + 32);
          if ( v8 )
          {
            if ( !_stricmp(v8, *(const char **)(*((_QWORD *)a2 + 4) + 24 * i + 16)) )
              lParam = *(WCHAR **)(*((_QWORD *)a2 + 4) + 24 * i);
          }
        }
      }
      for ( j = 0; (unsigned int)j < 2; j = (unsigned int)(j + 1) )
      {
        v10 = uID[j];
        Buffer[0] = 0;
        LoadStringW(HinstDll, v10, Buffer, 512);
        SendDlgItemMessageW(hDlg, 1112, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)Buffer);
      }
      if ( *(_QWORD *)(v4 + 32) )
      {
        if ( lParam )
          goto LABEL_18;
        v11 = 6358;
      }
      else
      {
        if ( lParam )
          goto LABEL_18;
        v11 = 6364;
      }
      Buffer[0] = 0;
      LoadStringW(HinstDll, v11, Buffer, 512);
      lParam = Buffer;
LABEL_18:
      v12 = SendDlgItemMessageW(hDlg, 1112, 0x158u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)lParam);
      if ( v12 != -1 )
        SendDlgItemMessageW(hDlg, 1112, 0x14Eu, v12, 0);
    }
  }
}

```

## disassembly

```asm
0x180021810  test    rcx, rcx
0x180021813  jz      locret_1800219EB
0x180021819  mov     [rsp-8+arg_10], rbx
0x18002181e  mov     [rsp-8+arg_18], rsi
0x180021823  push    rbp
0x180021824  push    rdi
0x180021825  push    r13
0x180021827  push    r14
0x180021829  push    r15
0x18002182b  lea     rbp, [rsp-350h]
0x180021833  sub     rsp, 450h
0x18002183a  mov     rax, cs:__security_cookie
0x180021841  xor     rax, rsp
0x180021844  mov     [rbp+370h+var_30], rax
0x18002184b  mov     [rsp+470h+uID], 18D6h
0x180021853  mov     rdi, rdx
0x180021856  mov     [rsp+470h+var_43C], 18DCh
0x18002185e  mov     rsi, rcx
0x180021861  test    rdx, rdx
0x180021864  jz      loc_1800219C1
0x18002186a  mov     r13, [rdx]
0x18002186d  xor     ebx, ebx
0x18002186f  mov     edx, 458h; nIDDlgItem
0x180021874  mov     [rsp+470h+lParam], rbx; lParam
0x180021879  xor     r9d, r9d; wParam
0x18002187c  mov     r8d, 14Bh; Msg
0x180021882  call    cs:__imp_SendDlgItemMessageA
0x180021888  xor     r14d, r14d
0x18002188b  cmp     [rdi+18h], ebx
0x18002188e  jbe     short loc_1800218ED
0x180021890  mov     rax, [rdi+20h]
0x180021894  lea     r15, [r14+r14*2]
0x180021898  cmp     dword ptr [rax+r15*8+8], 0
0x18002189e  jnz     short loc_1800218E4
0x1800218a0  mov     rax, [rax+r15*8]
0x1800218a4  xor     r9d, r9d; wParam
0x1800218a7  mov     edx, 458h; nIDDlgItem
0x1800218ac  mov     [rsp+470h+lParam], rax; lParam
0x1800218b1  mov     r8d, 143h; Msg
0x1800218b7  mov     rcx, rsi; hDlg
0x1800218ba  call    cs:__imp_SendDlgItemMessageW
0x1800218c0  mov     rcx, [r13+20h]; String1
0x1800218c4  test    rcx, rcx
0x1800218c7  jz      short loc_1800218E4
0x1800218c9  mov     rdx, [rdi+20h]
0x1800218cd  mov     rdx, [rdx+r15*8+10h]; String2
0x1800218d2  call    cs:__imp__stricmp
0x1800218d8  test    eax, eax
0x1800218da  jnz     short loc_1800218E4
0x1800218dc  mov     rax, [rdi+20h]
0x1800218e0  mov     rbx, [rax+r15*8]
0x1800218e4  inc     r14d
0x1800218e7  cmp     r14d, [rdi+18h]
0x1800218eb  jb      short loc_180021890
0x1800218ed  xor     edi, edi
0x1800218ef  mov     r14d, 200h
0x1800218f5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800218f9  cmp     edi, 2
0x1800218fc  jnb     short loc_180021943
0x1800218fe  mov     edx, [rsp+rdi*4+470h+uID]; uID
0x180021902  lea     r8, [rsp+470h+Buffer]; lpBuffer
0x180021907  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18002190e  xor     eax, eax
0x180021910  mov     r9d, r14d; cchBufferMax
0x180021913  mov     [rsp+470h+Buffer], ax
0x180021918  call    cs:__imp_LoadStringW
0x18002191e  lea     rax, [rsp+470h+Buffer]
0x180021923  mov     r9, r15; wParam
0x180021926  mov     edx, 458h; nIDDlgItem
0x18002192b  mov     [rsp+470h+lParam], rax; lParam
0x180021930  mov     r8d, 14Ah; Msg
0x180021936  mov     rcx, rsi; hDlg
0x180021939  call    cs:__imp_SendDlgItemMessageW
0x18002193f  inc     edi
0x180021941  jmp     short loc_1800218F9
0x180021943  cmp     qword ptr [r13+20h], 0
0x180021948  jz      short loc_180021956
0x18002194a  test    rbx, rbx
0x18002194d  jnz     short loc_180021981
0x18002194f  mov     edx, 18D6h
0x180021954  jmp     short loc_180021960
0x180021956  test    rbx, rbx
0x180021959  jnz     short loc_180021981
0x18002195b  mov     edx, 18DCh; uID
0x180021960  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180021967  lea     r8, [rsp+470h+Buffer]; lpBuffer
0x18002196c  xor     eax, eax
0x18002196e  mov     r9d, r14d; cchBufferMax
0x180021971  mov     [rsp+470h+Buffer], ax
0x180021976  call    cs:__imp_LoadStringW
0x18002197c  lea     rbx, [rsp+470h+Buffer]
0x180021981  mov     [rsp+470h+lParam], rbx; lParam
0x180021986  mov     r9, r15; wParam
0x180021989  mov     ebx, 458h
0x18002198e  mov     r8d, 158h; Msg
0x180021994  mov     edx, ebx; nIDDlgItem
0x180021996  mov     rcx, rsi; hDlg
0x180021999  call    cs:__imp_SendDlgItemMessageW
0x18002199f  cmp     eax, r15d
0x1800219a2  jz      short loc_1800219C1
0x1800219a4  movsxd  r9, eax; wParam
0x1800219a7  mov     r8d, 14Eh; Msg
0x1800219ad  mov     edx, ebx; nIDDlgItem
0x1800219af  mov     [rsp+470h+lParam], 0; lParam
0x1800219b8  mov     rcx, rsi; hDlg
0x1800219bb  call    cs:__imp_SendDlgItemMessageW
0x1800219c1  mov     rcx, [rbp+370h+var_30]
0x1800219c8  xor     rcx, rsp; StackCookie
0x1800219cb  call    __security_check_cookie
0x1800219d0  lea     r11, [rsp+470h+var_20]
0x1800219d8  mov     rbx, [r11+40h]
0x1800219dc  mov     rsi, [r11+48h]
0x1800219e0  mov     rsp, r11
0x1800219e3  pop     r15
0x1800219e5  pop     r14
0x1800219e7  pop     r13
0x1800219e9  pop     rdi
0x1800219ea  pop     rbp
0x1800219eb  retn
```
