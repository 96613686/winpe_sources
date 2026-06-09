# _TlgEnableCallback(x,x,x,x,x,x,x,x,x)

- ea: `0x10008be0`
- end: `0x10008c56`
- name: `__TlgEnableCallback@36`
- size: `118`
- prototype: `void __stdcall(LPCGUID pSourceId, ULONG callbackType, UCHAR level, ULONGLONG keywordAny, ULONGLONG keywordAll, PEVENT_FILTER_DESCRIPTOR pFilterData, PVOID pCallbackContext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x10008be0`

## pseudocode

```c
void __stdcall _TlgEnableCallback(
        LPCGUID pSourceId,
        ULONG callbackType,
        UCHAR level,
        ULONGLONG keywordAny,
        ULONGLONG keywordAll,
        PEVENT_FILTER_DESCRIPTOR pFilterData,
        PVOID pCallbackContext)
{
  int v7; // ecx
  void (__stdcall *v8)(LPCGUID, ULONG, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, PEVENT_FILTER_DESCRIPTOR, _DWORD); // ecx

  if ( pCallbackContext )
  {
    if ( callbackType )
    {
      if ( callbackType == 1 )
      {
        if ( level )
          v7 = level + 1;
        else
          v7 = 256;
        *(_DWORD *)pCallbackContext = v7;
        *((_QWORD *)pCallbackContext + 1) = keywordAny;
        *((_QWORD *)pCallbackContext + 2) = keywordAll;
      }
    }
    else
    {
      *(_DWORD *)pCallbackContext = 0;
    }
    v8 = (void (__stdcall *)(LPCGUID, ULONG, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, PEVENT_FILTER_DESCRIPTOR, _DWORD))*((_DWORD *)pCallbackContext + 8);
    if ( v8 )
      v8(
        pSourceId,
        callbackType,
        level,
        keywordAny,
        HIDWORD(keywordAny),
        keywordAll,
        HIDWORD(keywordAll),
        pFilterData,
        *((_DWORD *)pCallbackContext + 9));
  }
}

```

## disassembly

```asm
0x10008be0  mov     eax, [esp+pCallbackContext]
0x10008be4  test    eax, eax
0x10008be6  jz      short locret_10008C53
0x10008be8  mov     ecx, [esp+callbackType]
0x10008bec  mov     edx, dword ptr [esp+level]
0x10008bf0  push    ebx
0x10008bf1  mov     ebx, dword ptr [esp+4+keywordAll]
0x10008bf5  push    ebp
0x10008bf6  mov     ebp, dword ptr [esp+8+keywordAny+4]
0x10008bfa  push    edi
0x10008bfb  mov     edi, dword ptr [esp+0Ch+keywordAll+4]
0x10008bff  sub     ecx, 0
0x10008c02  jz      short loc_10008C2A
0x10008c04  dec     ecx
0x10008c05  jnz     short loc_10008C30
0x10008c07  test    dl, dl
0x10008c09  jz      short loc_10008C11
0x10008c0b  movzx   ecx, dl
0x10008c0e  inc     ecx
0x10008c0f  jmp     short loc_10008C16
0x10008c11  mov     ecx, 100h
0x10008c16  mov     [eax], ecx
0x10008c18  mov     ecx, dword ptr [esp+0Ch+keywordAny]
0x10008c1c  mov     [eax+8], ecx
0x10008c1f  mov     [eax+0Ch], ebp
0x10008c22  mov     [eax+10h], ebx
0x10008c25  mov     [eax+14h], edi
0x10008c28  jmp     short loc_10008C30
0x10008c2a  mov     dword ptr [eax], 0
0x10008c30  mov     ecx, [eax+20h]
0x10008c33  test    ecx, ecx
0x10008c35  jz      short loc_10008C50
0x10008c37  push    dword ptr [eax+24h]
0x10008c3a  push    [esp+10h+pFilterData]
0x10008c3e  push    edi
0x10008c3f  push    ebx
0x10008c40  push    ebp
0x10008c41  push    dword ptr [esp+20h+keywordAny]
0x10008c45  push    edx
0x10008c46  push    [esp+28h+callbackType]
0x10008c4a  push    [esp+2Ch+pSourceId]
0x10008c4e  call    ecx
0x10008c50  pop     edi
0x10008c51  pop     ebp
0x10008c52  pop     ebx
0x10008c53  retn    24h ; '$'
```
