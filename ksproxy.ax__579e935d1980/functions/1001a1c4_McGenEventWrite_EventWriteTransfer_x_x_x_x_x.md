# McGenEventWrite_EventWriteTransfer(x,x,x,x,x)

- ea: `0x1001a1c4`
- end: `0x1001a20c`
- name: `_McGenEventWrite_EventWriteTransfer@20`
- size: `72`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1001a270`
- `0x1001a516`
- `0x1001b660`
- `0x1001c490`

## callees

- `0x1001a1c4`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1001a1ff`
- `ADVAPI32!EventWriteTransfer` at `0x1001a1ff`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        int a1,
        const EVENT_DESCRIPTOR *a2,
        int a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // edi
  int v7; // edx
  ULONG v8; // edi

  v5 = *(unsigned __int16 **)(a1 + 8);
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
  return EventWriteTransfer(*(_QWORD *)a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1001a1c4  mov     edi, edi
0x1001a1c6  push    ebp
0x1001a1c7  mov     ebp, esp
0x1001a1c9  push    ebx
0x1001a1ca  push    esi
0x1001a1cb  mov     esi, [ebp+UserData]
0x1001a1ce  xor     eax, eax
0x1001a1d0  push    edi
0x1001a1d1  mov     edi, [ecx+8]
0x1001a1d4  mov     ebx, edx
0x1001a1d6  mov     [esi+4], eax
0x1001a1d9  test    edi, edi
0x1001a1db  jnz     short loc_1001A1E5
0x1001a1dd  mov     [esi], eax
0x1001a1df  mov     edx, eax
0x1001a1e1  mov     edi, eax
0x1001a1e3  jmp     short loc_1001A1ED
0x1001a1e5  push    2
0x1001a1e7  mov     [esi], edi
0x1001a1e9  movzx   edi, word ptr [edi]
0x1001a1ec  pop     edx
0x1001a1ed  push    esi; UserData
0x1001a1ee  push    [ebp+UserDataCount]; UserDataCount
0x1001a1f1  mov     [esi+8], edi
0x1001a1f4  push    eax; RelatedActivityId
0x1001a1f5  push    eax; ActivityId
0x1001a1f6  push    ebx; EventDescriptor
0x1001a1f7  mov     [esi+0Ch], edx
0x1001a1fa  push    dword ptr [ecx+4]
0x1001a1fd  push    dword ptr [ecx]; RegHandle
0x1001a1ff  call    ds:__imp__EventWriteTransfer@28; EventWriteTransfer(x,x,x,x,x,x,x)
0x1001a205  pop     edi
0x1001a206  pop     esi
0x1001a207  pop     ebx
0x1001a208  pop     ebp
0x1001a209  retn    0Ch
```
