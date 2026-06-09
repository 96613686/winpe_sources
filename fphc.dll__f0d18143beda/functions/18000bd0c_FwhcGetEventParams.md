# FwhcGetEventParams

- ea: `0x18000bd0c`
- end: `0x18000be29`
- name: `FwhcGetEventParams`
- size: `285`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008d7c`
- `0x18000b548`
- `0x18000b790`

## callees

- `0x18000bd0c`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18000be11`
- `fwpuclnt!FwpmEngineClose0` at `0x18000be11`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000be01`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000be01`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000bd9e`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000bd9e`
- `fwpuclnt!FwpmFilterGetById0` at `0x18000bdc4`
- `fwpuclnt!FwpmFilterGetById0` at `0x18000bdc4`

## pseudocode

```c
__int64 __fastcall FwhcGetEventParams(__int64 a1, __int64 a2)
{
  signed int v2; // ebx
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  UINT64 v8; // rdi
  signed int v9; // eax
  signed int v10; // eax
  GUID *providerKey; // rcx
  GUID v12; // xmm0
  FWPM_FILTER0 *filter; // [rsp+40h] [rbp+8h] BYREF
  HANDLE engineHandle; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  *(_BYTE *)(a2 + 16) = 0;
  engineHandle = 0;
  filter = 0;
  *(_QWORD *)(a2 + 36) = *(_QWORD *)a1;
  v4 = *(_DWORD *)(a1 + 136);
  if ( v4 && (v5 = v4 - 1) != 0 && (v6 = v5 - 1) != 0 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        return (unsigned int)v2;
      v8 = *(_QWORD *)(*(_QWORD *)(a1 + 144) + 16LL);
    }
    else
    {
      v8 = **(_QWORD **)(a1 + 144);
    }
  }
  else
  {
    v8 = *(_QWORD *)(*(_QWORD *)(a1 + 144) + 56LL);
  }
  if ( v8 )
  {
    v9 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
    v2 = v9;
    if ( v9 > 0 )
      v2 = (unsigned __int16)v9 | 0x80070000;
    if ( v2 >= 0 )
    {
      v10 = FwpmFilterGetById0(engineHandle, v8, &filter);
      v2 = v10;
      if ( v10 > 0 )
        v2 = (unsigned __int16)v10 | 0x80070000;
      if ( v2 >= 0 && filter )
      {
        providerKey = filter->providerKey;
        if ( providerKey )
        {
          v12 = *providerKey;
          *(_BYTE *)(a2 + 16) = 1;
          *(GUID *)(a2 + 20) = v12;
        }
        FwpmFreeMemory0((void **)&filter);
      }
      if ( engineHandle )
        FwpmEngineClose0(engineHandle);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000bd0c  mov     rax, rsp
0x18000bd0f  mov     [rax+18h], rbx
0x18000bd13  mov     [rax+20h], rsi
0x18000bd17  push    rdi
0x18000bd18  sub     rsp, 30h
0x18000bd1c  xor     ebx, ebx
0x18000bd1e  mov     rsi, rdx
0x18000bd21  mov     [rdx+10h], bl
0x18000bd24  mov     [rax+10h], rbx
0x18000bd28  mov     [rax+8], rbx
0x18000bd2c  mov     rax, [rcx]
0x18000bd2f  mov     [rdx+24h], rax
0x18000bd33  mov     r8d, [rcx+88h]
0x18000bd3a  test    r8d, r8d
0x18000bd3d  jz      short loc_18000BD74
0x18000bd3f  sub     r8d, 1
0x18000bd43  jz      short loc_18000BD74
0x18000bd45  sub     r8d, 1
0x18000bd49  jz      short loc_18000BD74
0x18000bd4b  sub     r8d, 1
0x18000bd4f  jz      short loc_18000BD68
0x18000bd51  cmp     r8d, 1
0x18000bd55  jnz     loc_18000BE17
0x18000bd5b  mov     rax, [rcx+90h]
0x18000bd62  mov     rdi, [rax+10h]
0x18000bd66  jmp     short loc_18000BD7F
0x18000bd68  mov     rax, [rcx+90h]
0x18000bd6f  mov     rdi, [rax]
0x18000bd72  jmp     short loc_18000BD7F
0x18000bd74  mov     rax, [rcx+90h]
0x18000bd7b  mov     rdi, [rax+38h]
0x18000bd7f  test    rdi, rdi
0x18000bd82  jz      loc_18000BE17
0x18000bd88  xor     r9d, r9d; session
0x18000bd8b  lea     rax, [rsp+38h+arg_8]
0x18000bd90  xor     r8d, r8d; authIdentity
0x18000bd93  mov     [rsp+38h+engineHandle], rax; engineHandle
0x18000bd98  xor     ecx, ecx; serverName
0x18000bd9a  lea     edx, [r9+0Ah]; authnService
0x18000bd9e  call    cs:__imp_FwpmEngineOpen0
0x18000bda4  mov     ebx, eax
0x18000bda6  test    eax, eax
0x18000bda8  jle     short loc_18000BDB3
0x18000bdaa  movzx   ebx, ax
0x18000bdad  or      ebx, 80070000h
0x18000bdb3  test    ebx, ebx
0x18000bdb5  js      short loc_18000BE17
0x18000bdb7  mov     rcx, [rsp+38h+arg_8]; engineHandle
0x18000bdbc  lea     r8, [rsp+38h+filter]; filter
0x18000bdc1  mov     rdx, rdi; id
0x18000bdc4  call    cs:__imp_FwpmFilterGetById0
0x18000bdca  mov     ebx, eax
0x18000bdcc  test    eax, eax
0x18000bdce  jle     short loc_18000BDD9
0x18000bdd0  movzx   ebx, ax
0x18000bdd3  or      ebx, 80070000h
0x18000bdd9  test    ebx, ebx
0x18000bddb  js      short loc_18000BE07
0x18000bddd  mov     rax, [rsp+38h+filter]
0x18000bde2  test    rax, rax
0x18000bde5  jz      short loc_18000BE07
0x18000bde7  mov     rcx, [rax+28h]
0x18000bdeb  test    rcx, rcx
0x18000bdee  jz      short loc_18000BDFC
0x18000bdf0  movups  xmm0, xmmword ptr [rcx]
0x18000bdf3  mov     byte ptr [rsi+10h], 1
0x18000bdf7  movdqu  xmmword ptr [rsi+14h], xmm0
0x18000bdfc  lea     rcx, [rsp+38h+filter]; p
0x18000be01  call    cs:__imp_FwpmFreeMemory0
0x18000be07  mov     rcx, [rsp+38h+arg_8]; engineHandle
0x18000be0c  test    rcx, rcx
0x18000be0f  jz      short loc_18000BE17
0x18000be11  call    cs:__imp_FwpmEngineClose0
0x18000be17  mov     rsi, [rsp+38h+arg_18]
0x18000be1c  mov     eax, ebx
0x18000be1e  mov     rbx, [rsp+38h+arg_10]
0x18000be23  add     rsp, 30h
0x18000be27  pop     rdi
0x18000be28  retn
```
