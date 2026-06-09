# DuUpdateConnectStatus

- ea: `0x18002613c`
- end: `0x18002620f`
- name: `DuUpdateConnectStatus`
- size: `211`
- prototype: `const WCHAR *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180024664`
- `0x180024b30`

## callees

- `0x18002613c`
- `0x18003c43c`
- `0x180041c9c`
- `0x180048048`
- `0x18004807c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800261eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800261f9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800261eb`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800261f9`
- `USER32!SendMessageW` at `0x18002617a`
- `USER32!SendMessageW` at `0x18002617a`
- `USER32!SetWindowTextW` at `0x1800261e2`
- `USER32!SetWindowTextW` at `0x1800261e2`
- `rtutils!TracePrintfExA` at `0x180026165`
- `rtutils!TracePrintfExA` at `0x180026165`

## string_xrefs

- `0x180026159`: `DuUpdateConnectStatus`

## pseudocode

```c
const WCHAR *__fastcall DuUpdateConnectStatus(__int64 a1)
{
  const WCHAR *result; // rax
  int v3; // edi
  PCNZWCH *v4; // rsi
  WCHAR *Psz; // rdi
  __int64 v6; // rax
  HINSTANCE v7; // rcx
  WCHAR *v8; // rsi

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DuUpdateConnectStatus");
  result = (const WCHAR *)SendMessageW(*(HWND *)(a1 + 32), 0x147u, 0, 0);
  v3 = (int)result;
  if ( (int)result >= 0 )
  {
    result = (const WCHAR *)ComboBox_GetItemDataPtr(*(HWND *)(a1 + 32), (int)result);
    v4 = (PCNZWCH *)result;
    if ( result )
    {
      Psz = ComboBox_GetPsz(*(HWND *)(a1 + 32), v3);
      v6 = HrasconnFromEntry(*v4, Psz);
      v7 = g_hinstDll;
      *(_QWORD *)(a1 + 320) = v6;
      result = (const WCHAR *)PszFromId(v7, (unsigned int)(v6 != 0) + 228);
      v8 = (WCHAR *)result;
      if ( result )
      {
        SetWindowTextW(*(HWND *)(a1 + 40), result);
        result = (const WCHAR *)GlobalFree(v8);
      }
      if ( Psz )
        return (const WCHAR *)GlobalFree(Psz);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002613c  mov     [rsp+arg_0], rbx
0x180026141  mov     [rsp+arg_8], rsi
0x180026146  push    rdi
0x180026147  sub     rsp, 20h
0x18002614b  mov     rbx, rcx
0x18002614e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180026154  cmp     ecx, 0FFFFFFFFh
0x180026157  jz      short loc_18002616B
0x180026159  lea     r8, aDuupdateconnec; "DuUpdateConnectStatus"
0x180026160  mov     edx, 0Ch; dwFlags
0x180026165  call    cs:__imp_TracePrintfExA
0x18002616b  mov     rcx, [rbx+20h]; hWnd
0x18002616f  xor     r9d, r9d; lParam
0x180026172  xor     r8d, r8d; wParam
0x180026175  mov     edx, 147h; Msg
0x18002617a  call    cs:__imp_SendMessageW
0x180026180  mov     rdi, rax
0x180026183  test    eax, eax
0x180026185  js      short loc_1800261FF
0x180026187  mov     rcx, [rbx+20h]
0x18002618b  mov     edx, edi
0x18002618d  call    ComboBox_GetItemDataPtr
0x180026192  mov     rsi, rax
0x180026195  test    rax, rax
0x180026198  jz      short loc_1800261FF
0x18002619a  mov     rcx, [rbx+20h]; hWnd
0x18002619e  mov     edx, edi
0x1800261a0  call    ComboBox_GetPsz
0x1800261a5  mov     rcx, [rsi]; lpString2
0x1800261a8  mov     rdx, rax; PCNZWCH
0x1800261ab  mov     rdi, rax
0x1800261ae  call    HrasconnFromEntry
0x1800261b3  mov     rcx, cs:g_hinstDll; hInstance
0x1800261ba  mov     [rbx+140h], rax
0x1800261c1  neg     rax
0x1800261c4  sbb     edx, edx
0x1800261c6  neg     edx
0x1800261c8  add     edx, 0E4h; uID
0x1800261ce  call    PszFromId
0x1800261d3  mov     rsi, rax
0x1800261d6  test    rax, rax
0x1800261d9  jz      short loc_1800261F1
0x1800261db  mov     rcx, [rbx+28h]; hWnd
0x1800261df  mov     rdx, rax; lpString
0x1800261e2  call    cs:__imp_SetWindowTextW
0x1800261e8  mov     rcx, rsi; hMem
0x1800261eb  call    cs:__imp_GlobalFree
0x1800261f1  test    rdi, rdi
0x1800261f4  jz      short loc_1800261FF
0x1800261f6  mov     rcx, rdi; hMem
0x1800261f9  call    cs:__imp_GlobalFree
0x1800261ff  mov     rbx, [rsp+28h+arg_0]
0x180026204  mov     rsi, [rsp+28h+arg_8]
0x180026209  add     rsp, 20h
0x18002620d  pop     rdi
0x18002620e  retn
```
