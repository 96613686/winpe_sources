# PmPowerCounterEnable(_DEVICE_EXTENSION *)

- ea: `0x14000d5a0`
- end: `0x14000d62b`
- name: `?PmPowerCounterEnable@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140007674`

## callees

- `0x14000d180`
- `0x14000d5a0`

## pseudocode

```c
__int64 __fastcall PmPowerCounterEnable(struct _DEVICE_EXTENSION *a1)
{
  _WORD *v1; // r8
  __int64 result; // rax
  unsigned int v4; // ecx
  int v5; // eax
  __int64 v6; // rax
  int v7; // edx

  v1 = (_WORD *)*((_QWORD *)a1 + 143);
  if ( !v1 )
    return 3221225485LL;
  v4 = *(_DWORD *)(*((_QWORD *)a1 + 29) + 28LL);
  if ( v4 - 12 <= 1 )
  {
    v7 = 0;
  }
  else if ( v4 <= 0xB && (v5 = 2862, _bittest(&v5, v4)) )
  {
    v6 = *((_QWORD *)a1 + 34);
    if ( v6 )
      v7 = (*(_BYTE *)(v6 + 8) != 0) + 1;
    else
      v7 = 2;
  }
  else
  {
    if ( v4 != 17 )
    {
      result = 0;
      *((_BYTE *)a1 + 1152) = 0;
      return result;
    }
    v7 = 3;
  }
  result = PmPowerContextInitialization(v1, v7);
  if ( (int)result >= 0 )
    *((_BYTE *)a1 + 1152) = 1;
  return result;
}

```

## disassembly

```asm
0x14000d5a0  push    rbx
0x14000d5a2  sub     rsp, 20h
0x14000d5a6  mov     r8, [rcx+478h]
0x14000d5ad  mov     rbx, rcx
0x14000d5b0  test    r8, r8
0x14000d5b3  jnz     short loc_14000D5BC
0x14000d5b5  mov     eax, 0C000000Dh
0x14000d5ba  jmp     short loc_14000D624
0x14000d5bc  mov     rax, [rcx+0E8h]
0x14000d5c3  mov     ecx, [rax+1Ch]
0x14000d5c6  lea     eax, [rcx-0Ch]
0x14000d5c9  cmp     eax, 1
0x14000d5cc  jbe     short loc_14000D60F
0x14000d5ce  cmp     ecx, 0Bh
0x14000d5d1  ja      short loc_14000D5FB
0x14000d5d3  mov     eax, 0B2Eh
0x14000d5d8  bt      eax, ecx
0x14000d5db  jnb     short loc_14000D5FB
0x14000d5dd  mov     rax, [rbx+110h]
0x14000d5e4  test    rax, rax
0x14000d5e7  jnz     short loc_14000D5EE
0x14000d5e9  lea     edx, [rax+2]
0x14000d5ec  jmp     short loc_14000D611
0x14000d5ee  mov     al, [rax+8]
0x14000d5f1  neg     al
0x14000d5f3  sbb     edx, edx
0x14000d5f5  neg     edx
0x14000d5f7  inc     edx
0x14000d5f9  jmp     short loc_14000D611
0x14000d5fb  cmp     ecx, 11h
0x14000d5fe  jnz     short loc_14000D605
0x14000d600  lea     edx, [rcx-0Eh]
0x14000d603  jmp     short loc_14000D611
0x14000d605  xor     eax, eax
0x14000d607  mov     [rbx+480h], al
0x14000d60d  jmp     short loc_14000D624
0x14000d60f  xor     edx, edx
0x14000d611  mov     rcx, r8
0x14000d614  call    ?PmPowerContextInitialization@@YAJPEAU_DISK_POWER_CONTEXT@@W4_DISK_DEVICEPOWER_TYPE@@@Z; PmPowerContextInitialization(_DISK_POWER_CONTEXT *,_DISK_DEVICEPOWER_TYPE)
0x14000d619  test    eax, eax
0x14000d61b  js      short loc_14000D624
0x14000d61d  mov     byte ptr [rbx+480h], 1
0x14000d624  add     rsp, 20h
0x14000d628  pop     rbx
0x14000d629  retn
```
