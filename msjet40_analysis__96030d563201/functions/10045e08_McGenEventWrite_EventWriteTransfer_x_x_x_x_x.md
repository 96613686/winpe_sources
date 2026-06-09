# McGenEventWrite_EventWriteTransfer(x,x,x,x,x)

- ea: `0x10045e08`
- end: `0x10045e57`
- name: `_McGenEventWrite_EventWriteTransfer@20`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10045e5d`

## callees

- `0x10045e08`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10045e4b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10045e4b`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        int a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        int a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // esi
  int v7; // edx
  ULONG v8; // esi

  v5 = (unsigned __int16 *)dword_1012B440;
  HIDWORD(UserData->Ptr) = 0;
  if ( v5 )
  {
    LODWORD(UserData->Ptr) = v5;
    v8 = *v5;
    v7 = 2;
  }
  else
  {
    LODWORD(UserData->Ptr) = 0;
    v7 = 0;
    v8 = 0;
  }
  UserData->Size = v8;
  UserData->Reserved = v7;
  return EventWriteTransfer(Microsoft_Windows_JetRed_Context, a2, 0, 0, 3u, UserData);
}

```

## disassembly

```asm
0x10045e08  mov     edi, edi
0x10045e0a  push    ebp
0x10045e0b  mov     ebp, esp
0x10045e0d  mov     ecx, [ebp+UserData]
0x10045e10  xor     eax, eax
0x10045e12  push    esi
0x10045e13  mov     esi, dword_1012B440
0x10045e19  push    edi
0x10045e1a  mov     [ecx+4], eax
0x10045e1d  mov     edi, edx
0x10045e1f  test    esi, esi
0x10045e21  jnz     short loc_10045E2B
0x10045e23  mov     [ecx], eax
0x10045e25  mov     edx, eax
0x10045e27  mov     esi, eax
0x10045e29  jmp     short loc_10045E33
0x10045e2b  push    2
0x10045e2d  mov     [ecx], esi
0x10045e2f  movzx   esi, word ptr [esi]
0x10045e32  pop     edx
0x10045e33  push    ecx; UserData
0x10045e34  push    3; UserDataCount
0x10045e36  push    eax; RelatedActivityId
0x10045e37  push    eax; ActivityId
0x10045e38  mov     [ecx+8], esi
0x10045e3b  push    edi; EventDescriptor
0x10045e3c  mov     [ecx+0Ch], edx
0x10045e3f  push    dword ptr _Microsoft_Windows_JetRed_Context+4
0x10045e45  push    dword ptr _Microsoft_Windows_JetRed_Context; RegHandle
0x10045e4b  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x10045e51  pop     edi
0x10045e52  pop     esi
0x10045e53  pop     ebp
0x10045e54  retn    0Ch
```
