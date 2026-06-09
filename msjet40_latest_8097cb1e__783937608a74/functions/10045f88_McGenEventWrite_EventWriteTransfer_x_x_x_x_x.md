# McGenEventWrite_EventWriteTransfer(x,x,x,x,x)

- ea: `0x10045f88`
- end: `0x10045fd7`
- name: `_McGenEventWrite_EventWriteTransfer@20`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10045fdd`

## callees

- `0x10045f88`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10045fcb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x10045fcb`

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

  v5 = (unsigned __int16 *)dword_1012B450;
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
0x10045f88  mov     edi, edi
0x10045f8a  push    ebp
0x10045f8b  mov     ebp, esp
0x10045f8d  mov     ecx, [ebp+UserData]
0x10045f90  xor     eax, eax
0x10045f92  push    esi
0x10045f93  mov     esi, dword_1012B450
0x10045f99  push    edi
0x10045f9a  mov     [ecx+4], eax
0x10045f9d  mov     edi, edx
0x10045f9f  test    esi, esi
0x10045fa1  jnz     short loc_10045FAB
0x10045fa3  mov     [ecx], eax
0x10045fa5  mov     edx, eax
0x10045fa7  mov     esi, eax
0x10045fa9  jmp     short loc_10045FB3
0x10045fab  push    2
0x10045fad  mov     [ecx], esi
0x10045faf  movzx   esi, word ptr [esi]
0x10045fb2  pop     edx
0x10045fb3  push    ecx; UserData
0x10045fb4  push    3; UserDataCount
0x10045fb6  push    eax; RelatedActivityId
0x10045fb7  push    eax; ActivityId
0x10045fb8  mov     [ecx+8], esi
0x10045fbb  push    edi; EventDescriptor
0x10045fbc  mov     [ecx+0Ch], edx
0x10045fbf  push    dword ptr _Microsoft_Windows_JetRed_Context+4
0x10045fc5  push    dword ptr _Microsoft_Windows_JetRed_Context; RegHandle
0x10045fcb  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x10045fd1  pop     edi
0x10045fd2  pop     esi
0x10045fd3  pop     ebp
0x10045fd4  retn    0Ch
```
