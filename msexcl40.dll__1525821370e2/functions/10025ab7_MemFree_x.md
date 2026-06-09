# MemFree(x)

- ea: `0x10025ab7`
- end: `0x10025b42`
- name: `_MemFree@4`
- size: `139`
- prototype: `void __thiscall(_DWORD *this)`
- caller_count: `97`
- callee_count: `4`
- tags: ``

## callers

- `0x10006840`
- `0x100068a0`
- `0x10006bd0`
- `0x10007090`
- `0x10007670`
- `0x10007740`
- `0x10007a00`
- `0x10008210`
- `0x100082d0`
- `0x100088e0`
- `0x100092a0`
- `0x100094b0`
- `0x100098e0`
- `0x10009aa0`
- `0x1000a4d0`
- `0x1000a6a0`
- `0x1000ab50`
- `0x1000b350`
- `0x1000c030`
- `0x1000d030`
- `0x1000d590`
- `0x1000daa0`
- `0x1000df70`
- `0x1000eec0`
- `0x1000f040`
- `0x1000fbf0`
- `0x1000fdf0`
- `0x10010790`
- `0x10011280`
- `0x10011730`
- `0x10011a70`
- `0x10011dd0`
- `0x10012270`
- `0x10013490`
- `0x10014020`
- `0x10015090`
- `0x100158d0`
- `0x10015ed0`
- `0x100168a0`
- `0x10016950`
- `0x10017110`
- `0x100175a0`
- `0x10017790`
- `0x10018550`
- `0x1001abf0`
- `0x1001b1e0`
- `0x1001b2f0`
- `0x1001b4b0`
- `0x1001b770`
- `0x1001bbd0`

## callees

- `0x10025797`
- `0x100259e1`
- `0x10025a47`
- `0x10025ab7`

## pseudocode

```c
void __thiscall MemFree(_DWORD *this)
{
  _DWORD *v1; // esi
  int v2; // edx
  int v3; // ecx
  int v4; // edi

  if ( this )
  {
    v1 = this - 3;
    v2 = *(this - 2);
    if ( v2 )
    {
      if ( *v1 == 1 )
      {
        FreeSpace((HGLOBAL)*(this - 1));
      }
      else
      {
        v3 = dword_1003AE64;
        v4 = 0;
        while ( 1 )
        {
          if ( !v3 )
          {
            v1[2] = dword_1003AE64;
            dword_1003AE64 = (int)v1;
            return;
          }
          if ( v1 == (_DWORD *)(v3 + *(_DWORD *)(v3 + 4)) )
          {
            *(_DWORD *)(v3 + 4) += v2;
            v1 = (_DWORD *)v3;
            goto LABEL_17;
          }
          if ( (_DWORD *)((char *)v1 + v2) == (_DWORD *)v3 )
            break;
          v4 = v3;
          v3 = *(_DWORD *)(v3 + 8);
        }
        if ( v4 )
          *(_DWORD *)(v4 + 8) = v1;
        else
          dword_1003AE64 = (int)v1;
        v1[2] = *(_DWORD *)(v3 + 8);
        v1[1] += *(_DWORD *)(v3 + 4);
LABEL_17:
        if ( AttemptToFreePage(v1) != 1 )
          AttemptToMerge(v1, v4);
      }
    }
  }
}

```

## disassembly

```asm
0x10025ab7  test    ecx, ecx
0x10025ab9  jz      short locret_10025B07
0x10025abb  push    esi
0x10025abc  lea     esi, [ecx-0Ch]
0x10025abf  mov     edx, [esi+4]
0x10025ac2  test    edx, edx
0x10025ac4  jz      short loc_10025B06
0x10025ac6  cmp     dword ptr [esi], 1
0x10025ac9  jnz     short loc_10025AD4
0x10025acb  mov     ecx, [ecx-4]; hMem
0x10025ace  pop     esi
0x10025acf  jmp     _FreeSpace@4; FreeSpace(x)
0x10025ad4  push    ebx
0x10025ad5  mov     ebx, dword_1003AE64
0x10025adb  mov     ecx, ebx
0x10025add  push    edi
0x10025ade  xor     edi, edi
0x10025ae0  jmp     short loc_10025AF7
0x10025ae2  mov     eax, [ecx+4]
0x10025ae5  add     eax, ecx
0x10025ae7  cmp     esi, eax
0x10025ae9  jz      short loc_10025B25
0x10025aeb  lea     eax, [edx+esi]
0x10025aee  cmp     eax, ecx
0x10025af0  jz      short loc_10025B08
0x10025af2  mov     edi, ecx
0x10025af4  mov     ecx, [ecx+8]
0x10025af7  test    ecx, ecx
0x10025af9  jnz     short loc_10025AE2
0x10025afb  mov     [esi+8], ebx
0x10025afe  mov     dword_1003AE64, esi
0x10025b04  pop     edi
0x10025b05  pop     ebx
0x10025b06  pop     esi
0x10025b07  retn
0x10025b08  test    edi, edi
0x10025b0a  jnz     short loc_10025B14
0x10025b0c  mov     dword_1003AE64, esi
0x10025b12  jmp     short loc_10025B17
0x10025b14  mov     [edi+8], esi
0x10025b17  mov     eax, [ecx+8]
0x10025b1a  mov     [esi+8], eax
0x10025b1d  mov     eax, [ecx+4]
0x10025b20  add     [esi+4], eax
0x10025b23  jmp     short loc_10025B2A
0x10025b25  add     [ecx+4], edx
0x10025b28  mov     esi, ecx
0x10025b2a  mov     ecx, esi
0x10025b2c  call    AttemptToFreePage
0x10025b31  cmp     eax, 1
0x10025b34  jz      short loc_10025B04
0x10025b36  mov     edx, edi
0x10025b38  mov     ecx, esi
0x10025b3a  pop     edi
0x10025b3b  pop     ebx
0x10025b3c  pop     esi
0x10025b3d  jmp     AttemptToMerge
```
