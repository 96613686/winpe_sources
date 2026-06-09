# KsGetMediaTypeCount(x,x,x)

- ea: `0x1001ff00`
- end: `0x1001ff95`
- name: `_KsGetMediaTypeCount@12`
- size: `149`
- prototype: `int __stdcall(HANDLE hDevice, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10017b90`
- `0x10017be0`
- `0x1001e1f8`
- `0x100208f4`

## callees

- `0x1001fbb0`
- `0x1001ff00`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1001ff85`
- `ole32!CoTaskMemFree` at `0x1001ff85`

## pseudocode

```c
int __stdcall KsGetMediaTypeCount(HANDLE hDevice, int a2, _DWORD *a3)
{
  int MultiplePinFactoryItems; // esi
  _DWORD *v4; // ecx
  char *v5; // edx
  int v6; // eax
  int v7; // eax
  LPVOID pv; // [esp+Ch] [ebp-4h] BYREF

  pv = 0;
  MultiplePinFactoryItems = KsGetMultiplePinFactoryItems(hDevice, a2, 13, &pv);
  if ( MultiplePinFactoryItems >= 0
    || (MultiplePinFactoryItems = KsGetMultiplePinFactoryItems(hDevice, a2, 3, &pv), MultiplePinFactoryItems >= 0) )
  {
    v4 = pv;
    v5 = (char *)pv + 8;
    *a3 = *((_DWORD *)pv + 1);
    while ( 1 )
    {
      v7 = v4[1];
      if ( !v7 )
        break;
      v6 = v7 - 1;
      v4[1] = v6;
      if ( (v5[4] & 2) != 0 )
      {
        v4[1] = v6 - 1;
        --*a3;
        v5 += (*(_DWORD *)v5 + 7) & 0xFFFFFFF8;
      }
      v5 += (*(_DWORD *)v5 + 7) & 0xFFFFFFF8;
    }
    v4[1] = -1;
    CoTaskMemFree(v4);
  }
  return MultiplePinFactoryItems;
}

```

## disassembly

```asm
0x1001ff00  mov     edi, edi
0x1001ff02  push    ebp
0x1001ff03  mov     ebp, esp
0x1001ff05  and     esp, 0FFFFFFF8h
0x1001ff08  push    ecx
0x1001ff09  push    ecx
0x1001ff0a  push    esi
0x1001ff0b  push    edi
0x1001ff0c  lea     eax, [esp+10h+pv]
0x1001ff10  mov     [esp+10h+pv], 0
0x1001ff18  push    eax; int
0x1001ff19  push    0Dh; int
0x1001ff1b  push    [ebp+arg_4]; int
0x1001ff1e  push    [ebp+hDevice]; hDevice
0x1001ff21  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x1001ff26  mov     esi, eax
0x1001ff28  test    esi, esi
0x1001ff2a  jns     short loc_1001FF44
0x1001ff2c  lea     eax, [esp+10h+pv]
0x1001ff30  push    eax; int
0x1001ff31  push    3; int
0x1001ff33  push    [ebp+arg_4]; int
0x1001ff36  push    [ebp+hDevice]; hDevice
0x1001ff39  call    _KsGetMultiplePinFactoryItems@16; KsGetMultiplePinFactoryItems(x,x,x,x)
0x1001ff3e  mov     esi, eax
0x1001ff40  test    esi, esi
0x1001ff42  js      short loc_1001FF8B
0x1001ff44  mov     ecx, [esp+10h+pv]
0x1001ff48  mov     edi, [ebp+arg_8]
0x1001ff4b  mov     eax, [ecx+4]
0x1001ff4e  lea     edx, [ecx+8]
0x1001ff51  mov     [edi], eax
0x1001ff53  jmp     short loc_1001FF79
0x1001ff55  dec     eax
0x1001ff56  mov     [ecx+4], eax
0x1001ff59  test    byte ptr [edx+4], 2
0x1001ff5d  jz      short loc_1001FF6F
0x1001ff5f  dec     eax
0x1001ff60  mov     [ecx+4], eax
0x1001ff63  dec     dword ptr [edi]
0x1001ff65  mov     eax, [edx]
0x1001ff67  add     eax, 7
0x1001ff6a  and     eax, 0FFFFFFF8h
0x1001ff6d  add     edx, eax
0x1001ff6f  mov     eax, [edx]
0x1001ff71  add     eax, 7
0x1001ff74  and     eax, 0FFFFFFF8h
0x1001ff77  add     edx, eax
0x1001ff79  mov     eax, [ecx+4]
0x1001ff7c  test    eax, eax
0x1001ff7e  jnz     short loc_1001FF55
0x1001ff80  dec     eax
0x1001ff81  push    ecx; pv
0x1001ff82  mov     [ecx+4], eax
0x1001ff85  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001ff8b  pop     edi
0x1001ff8c  mov     eax, esi
0x1001ff8e  pop     esi
0x1001ff8f  mov     esp, ebp
0x1001ff91  pop     ebp
0x1001ff92  retn    0Ch
```
