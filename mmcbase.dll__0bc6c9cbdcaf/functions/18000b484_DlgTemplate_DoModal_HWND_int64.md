# DlgTemplate::DoModal(HWND__ *,__int64 &)

- ea: `0x18000b484`
- end: `0x18000b544`
- name: `?DoModal@DlgTemplate@@IEAAJPEAUHWND__@@AEA_J@Z`
- size: `192`
- prototype: `__int64 __fastcall(LPARAM dwInitParam, HWND hWndParent, __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba24`
- `0x180010020`

## callees

- `0x18000b484`
- `0x18000b6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b508`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b508`
- `USER32!DialogBoxIndirectParamW` at `0x18000b4f0`
- `USER32!DialogBoxIndirectParamW` at `0x18000b4f0`

## pseudocode

```c
int __fastcall DlgTemplate::DoModal(LPARAM dwInitParam, HWND hWndParent, __int64 *a3)
{
  bool v3; // zf
  int result; // eax
  int v8; // ecx
  HINSTANCE v9; // rcx
  const DLGTEMPLATE *v10; // rdx
  INT_PTR v11; // rax
  struct ResourceCache::_resourceDefinition near **v12; // [rsp+60h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(dwInitParam + 8) == 0;
  *a3 = 0;
  if ( !v3 )
    return -2147024726;
  v8 = *(_DWORD *)(dwInitParam + 32);
  v12 = 0;
  result = ResourceCache::GetResourceEntry(v8, 1, &v12);
  if ( result >= 0 )
  {
    v9 = ResourceCache::s_hResourceInstance;
    v10 = (const DLGTEMPLATE *)v12[2];
    *(_QWORD *)(dwInitParam + 24) = ResourceCache::s_hResourceInstance;
    v11 = DialogBoxIndirectParamW(v9, v10, hWndParent, DlgTemplate::DialogProc, dwInitParam);
    if ( v11 )
    {
      if ( v11 == -1 )
      {
        result = GetLastError();
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        if ( result >= 0 )
          result = -2147418113;
      }
      else
      {
        *a3 = v11;
        result = 0;
      }
    }
    else
    {
      result = -2147024809;
    }
  }
  *(_QWORD *)(dwInitParam + 8) = 0;
  *(_QWORD *)(dwInitParam + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b484  push    rbx
0x18000b486  push    rbp
0x18000b487  push    rsi
0x18000b488  push    rdi
0x18000b489  sub     rsp, 38h
0x18000b48d  cmp     qword ptr [rcx+8], 0
0x18000b492  mov     rsi, r8
0x18000b495  mov     rbp, rdx
0x18000b498  mov     qword ptr [r8], 0
0x18000b49f  mov     rbx, rcx
0x18000b4a2  jz      short loc_18000B4AE
0x18000b4a4  mov     eax, 800700AAh
0x18000b4a9  jmp     loc_18000B53B
0x18000b4ae  mov     ecx, [rcx+20h]
0x18000b4b1  lea     r8, [rsp+58h+arg_0]
0x18000b4b6  mov     edx, 1
0x18000b4bb  mov     [rsp+58h+arg_0], 0
0x18000b4c4  call    ?GetResourceEntry@ResourceCache@@CAJW4ResourceEntry@1@W4ResourceType@1@AEAPEBU_resourceDefinition@1@@Z; ResourceCache::GetResourceEntry(ResourceCache::ResourceEntry,ResourceCache::ResourceType,ResourceCache::_resourceDefinition const * &)
0x18000b4c9  test    eax, eax
0x18000b4cb  js      short loc_18000B52B
0x18000b4cd  mov     rax, [rsp+58h+arg_0]
0x18000b4d2  lea     r9, ?DialogProc@DlgTemplate@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18000b4d9  mov     rcx, cs:?s_hResourceInstance@ResourceCache@@0PEAUHINSTANCE__@@EA; hInstance
0x18000b4e0  mov     r8, rbp; hWndParent
0x18000b4e3  mov     [rsp+58h+dwInitParam], rbx; dwInitParam
0x18000b4e8  mov     rdx, [rax+10h]; hDialogTemplate
0x18000b4ec  mov     [rbx+18h], rcx
0x18000b4f0  call    cs:__imp_DialogBoxIndirectParamW
0x18000b4f6  test    rax, rax
0x18000b4f9  jnz     short loc_18000B502
0x18000b4fb  mov     eax, 80070057h
0x18000b500  jmp     short loc_18000B52B
0x18000b502  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b506  jnz     short loc_18000B526
0x18000b508  call    cs:__imp_GetLastError
0x18000b50e  test    eax, eax
0x18000b510  jle     short loc_18000B51A
0x18000b512  movzx   eax, ax
0x18000b515  or      eax, 80070000h
0x18000b51a  test    eax, eax
0x18000b51c  mov     ecx, 8000FFFFh
0x18000b521  cmovns  eax, ecx
0x18000b524  jmp     short loc_18000B52B
0x18000b526  mov     [rsi], rax
0x18000b529  xor     eax, eax
0x18000b52b  mov     qword ptr [rbx+8], 0
0x18000b533  mov     qword ptr [rbx+18h], 0
0x18000b53b  add     rsp, 38h
0x18000b53f  pop     rdi
0x18000b540  pop     rsi
0x18000b541  pop     rbp
0x18000b542  pop     rbx
0x18000b543  retn
```
