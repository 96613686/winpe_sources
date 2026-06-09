# ScanAbortDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140010630`
- end: `0x14001075e`
- name: `?ScanAbortDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `302`
- prototype: `INT_PTR __fastcall(HWND, int, WPARAM, LONG_PTR)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140010630`
- `0x140016d7c`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x140010677`
- `USER32!SetDlgItemTextW` at `0x14001068f`
- `USER32!SetDlgItemTextW` at `0x1400106f7`
- `USER32!SetDlgItemTextW` at `0x140010677`
- `USER32!SetDlgItemTextW` at `0x14001068f`
- `USER32!SetDlgItemTextW` at `0x1400106f7`
- `USER32!SetWindowLongPtrW` at `0x1400106b0`
- `USER32!SetWindowLongPtrW` at `0x1400106cd`
- `USER32!SetWindowLongPtrW` at `0x1400106b0`
- `USER32!SetWindowLongPtrW` at `0x1400106cd`
- `USER32!SendDlgItemMessageW` at `0x140010727`
- `USER32!SendDlgItemMessageW` at `0x140010727`
- `USER32!GetWindowLongPtrW` at `0x140010734`
- `USER32!GetWindowLongPtrW` at `0x140010734`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010680`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140010680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010700`

## pseudocode

```c
INT_PTR __fastcall ScanAbortDlgProc(HWND a1, int a2, WPARAM a3, LONG_PTR a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  WCHAR *v11; // rbx
  LONG_PTR WindowLongPtrW; // rax

  v7 = a2 - 16;
  if ( !v7 )
    goto LABEL_13;
  v8 = v7 - 256;
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 == 752 )
      {
        if ( a4 )
        {
          SetDlgItemTextW(a1, 1012, (LPCWSTR)a4);
          CoTaskMemFree((LPVOID)a4);
        }
        else
        {
          SetDlgItemTextW(a1, 1012, &String);
        }
        SendDlgItemMessageW(a1, 1006, 0x402u, a3, 0);
        return 1;
      }
      return 0;
    }
LABEL_13:
    WindowLongPtrW = GetWindowLongPtrW(a1, 16);
    if ( WindowLongPtrW )
      *(_DWORD *)(WindowLongPtrW + 1768) = 1;
    return 1;
  }
  SetWindowLongPtrW(a1, 16, 0);
  if ( !a4 )
    return 0;
  SetWindowLongPtrW(a1, 16, a4);
  v11 = SHFormatMessage(0x6Cu, a4 + 536, *(unsigned __int16 *)(a4 + 16));
  SetDlgItemTextW(a1, 1005, v11);
  LocalFree(v11);
  SendDlgItemMessageW(a1, 1006, 0x401u, 0, (unsigned __int64)*(unsigned __int16 *)(a4 + 1736) << 16);
  return 1;
}

```

## disassembly

```asm
0x140010630  mov     [rsp+arg_0], rbx
0x140010635  mov     [rsp+arg_8], rsi
0x14001063a  push    rdi
0x14001063b  sub     rsp, 30h
0x14001063f  mov     rsi, r9
0x140010642  mov     rbx, r8
0x140010645  mov     rdi, rcx
0x140010648  sub     edx, 10h
0x14001064b  jz      loc_14001072F
0x140010651  sub     edx, 100h
0x140010657  jz      short loc_1400106A9
0x140010659  sub     edx, 1
0x14001065c  jz      loc_14001072F
0x140010662  cmp     edx, 2F0h
0x140010668  jnz     short loc_1400106BB
0x14001066a  mov     edx, 3F4h; nIDDlgItem
0x14001066f  test    r9, r9
0x140010672  jz      short loc_140010688
0x140010674  mov     r8, r9; lpString
0x140010677  call    cs:__imp_SetDlgItemTextW
0x14001067d  mov     rcx, rsi; pv
0x140010680  call    cs:__imp_CoTaskMemFree
0x140010686  jmp     short loc_140010695
0x140010688  lea     r8, String; lpString
0x14001068f  call    cs:__imp_SetDlgItemTextW
0x140010695  mov     [rsp+38h+lParam], 0
0x14001069e  mov     r9, rbx
0x1400106a1  mov     r8d, 402h
0x1400106a7  jmp     short loc_14001071F
0x1400106a9  xor     r8d, r8d; dwNewLong
0x1400106ac  lea     edx, [r8+10h]; nIndex
0x1400106b0  call    cs:__imp_SetWindowLongPtrW
0x1400106b6  test    rsi, rsi
0x1400106b9  jnz     short loc_1400106C2
0x1400106bb  xor     eax, eax
0x1400106bd  jmp     loc_14001074E
0x1400106c2  mov     r8, rsi; dwNewLong
0x1400106c5  mov     edx, 10h; nIndex
0x1400106ca  mov     rcx, rdi; hWnd
0x1400106cd  call    cs:__imp_SetWindowLongPtrW
0x1400106d3  movzx   r8d, word ptr [rsi+10h]
0x1400106d8  lea     rdx, [rsi+218h]
0x1400106df  mov     ecx, 6Ch ; 'l'; dwMessageId
0x1400106e4  call    ?SHFormatMessage@@YAPEAGKZZ; SHFormatMessage(ulong,...)
0x1400106e9  mov     r8, rax; lpString
0x1400106ec  mov     edx, 3EDh; nIDDlgItem
0x1400106f1  mov     rcx, rdi; hDlg
0x1400106f4  mov     rbx, rax
0x1400106f7  call    cs:__imp_SetDlgItemTextW
0x1400106fd  mov     rcx, rbx; hMem
0x140010700  call    cs:__imp_LocalFree
0x140010706  movzx   eax, word ptr [rsi+6C8h]
0x14001070d  mov     r8d, 401h; Msg
0x140010713  shl     rax, 10h
0x140010717  mov     [rsp+38h+lParam], rax; lParam
0x14001071c  xor     r9d, r9d; wParam
0x14001071f  mov     edx, 3EEh; nIDDlgItem
0x140010724  mov     rcx, rdi; hDlg
0x140010727  call    cs:__imp_SendDlgItemMessageW
0x14001072d  jmp     short loc_140010749
0x14001072f  mov     edx, 10h; nIndex
0x140010734  call    cs:__imp_GetWindowLongPtrW
0x14001073a  test    rax, rax
0x14001073d  jz      short loc_140010749
0x14001073f  mov     dword ptr [rax+6E8h], 1
0x140010749  mov     eax, 1
0x14001074e  mov     rbx, [rsp+38h+arg_0]
0x140010753  mov     rsi, [rsp+38h+arg_8]
0x140010758  add     rsp, 30h
0x14001075c  pop     rdi
0x14001075d  retn
```
