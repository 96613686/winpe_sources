# ConvertKsMediaTypeToAmMediaType(KSDATAFORMAT *,_AMMediaType *)

- ea: `0x1001b4c6`
- end: `0x1001b55a`
- name: `?ConvertKsMediaTypeToAmMediaType@@YGJPATKSDATAFORMAT@@PAU_AMMediaType@@@Z`
- size: `148`
- prototype: `int __cdecl(union KSDATAFORMAT *, struct _AMMediaType *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1001b660`
- `0x1001bb90`
- `0x1001c710`

## callees

- `0x1001b4c6`
- `0x1003bcf8`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001b51f`
- `ole32!CoTaskMemAlloc` at `0x1001b51f`

## pseudocode

```c
int __fastcall ConvertKsMediaTypeToAmMediaType(int *a1, _DWORD *a2)
{
  int v3; // eax
  void *v4; // ecx
  int result; // eax

  *a2 = a1[4];
  a2[1] = a1[5];
  a2[2] = a1[6];
  a2[3] = a1[7];
  a2[4] = a1[8];
  a2[5] = a1[9];
  a2[6] = a1[10];
  a2[7] = a1[11];
  a2[11] = a1[12];
  a2[12] = a1[13];
  a2[13] = a1[14];
  a2[14] = a1[15];
  a2[9] = a1[1] & 1;
  a2[10] = a1[2];
  a2[8] = a1[2] != 0;
  v3 = *a1;
  if ( (unsigned int)*a1 <= 0x40 )
  {
    a2[16] = 0;
    result = 0;
    a2[17] = 0;
  }
  else
  {
    a2[16] = v3 - 64;
    v4 = CoTaskMemAlloc(v3 - 64);
    a2[17] = v4;
    if ( v4 )
    {
      memcpy(v4, a1 + 16, a2[16]);
      return 0;
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1001b4c6  mov     edi, edi
0x1001b4c8  push    ebp
0x1001b4c9  mov     ebp, esp
0x1001b4cb  push    ecx
0x1001b4cc  push    ecx
0x1001b4cd  push    ebx
0x1001b4ce  push    esi
0x1001b4cf  push    edi
0x1001b4d0  mov     ebx, edx
0x1001b4d2  mov     [ebp+var_8], ecx
0x1001b4d5  mov     edi, ebx
0x1001b4d7  lea     esi, [ecx+10h]
0x1001b4da  xor     edx, edx
0x1001b4dc  mov     [ebp+var_4], edx
0x1001b4df  movsd
0x1001b4e0  movsd
0x1001b4e1  movsd
0x1001b4e2  movsd
0x1001b4e3  lea     esi, [ecx+20h]
0x1001b4e6  lea     edi, [ebx+10h]
0x1001b4e9  movsd
0x1001b4ea  movsd
0x1001b4eb  movsd
0x1001b4ec  movsd
0x1001b4ed  lea     esi, [ecx+30h]
0x1001b4f0  lea     edi, [ebx+2Ch]
0x1001b4f3  movsd
0x1001b4f4  movsd
0x1001b4f5  movsd
0x1001b4f6  movsd
0x1001b4f7  mov     eax, [ecx+4]
0x1001b4fa  and     eax, 1
0x1001b4fd  mov     [ebx+24h], eax
0x1001b500  mov     eax, [ecx+8]
0x1001b503  mov     [ebx+28h], eax
0x1001b506  xor     eax, eax
0x1001b508  cmp     [ecx+8], edx
0x1001b50b  setnz   al
0x1001b50e  mov     [ebx+20h], eax
0x1001b511  mov     eax, [ecx]
0x1001b513  cmp     eax, 40h ; '@'
0x1001b516  jbe     short loc_1001B54D
0x1001b518  add     eax, 0FFFFFFC0h
0x1001b51b  push    eax; cb
0x1001b51c  mov     [ebx+40h], eax
0x1001b51f  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001b525  mov     ecx, eax
0x1001b527  mov     [ebx+44h], ecx
0x1001b52a  test    ecx, ecx
0x1001b52c  jnz     short loc_1001B535
0x1001b52e  mov     eax, 8007000Eh
0x1001b533  jmp     short loc_1001B555
0x1001b535  push    dword ptr [ebx+40h]; Size
0x1001b538  mov     eax, [ebp+var_8]
0x1001b53b  add     eax, 40h ; '@'
0x1001b53e  push    eax; Src
0x1001b53f  push    ecx; void *
0x1001b540  call    _memcpy
0x1001b545  mov     eax, [ebp+var_4]
0x1001b548  add     esp, 0Ch
0x1001b54b  jmp     short loc_1001B555
0x1001b54d  mov     [ebx+40h], edx
0x1001b550  mov     eax, edx
0x1001b552  mov     [ebx+44h], edx
0x1001b555  pop     edi
0x1001b556  pop     esi
0x1001b557  pop     ebx
0x1001b558  leave
0x1001b559  retn
```
