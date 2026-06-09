# CPacketRadius::FillPacketHeaderInfo(_IASATTRIBUTE *)

- ea: `0x180013808`
- end: `0x1800138c0`
- name: `?FillPacketHeaderInfo@CPacketRadius@@AEAAJPEAU_IASATTRIBUTE@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(CPacketRadius *__hidden this, struct _IASATTRIBUTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012c68`

## callees

- `0x1800094e4`
- `0x180013808`
- `0x18001d31c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001381d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001381d`

## string_xrefs

- `0x180013851`: `Unable to allocate dynamic memory for packet header info during in-packet processing`

## pseudocode

```c
__int64 __fastcall CPacketRadius::FillPacketHeaderInfo(CPacketRadius *this, struct _IASATTRIBUTE *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rdx
  __int64 result; // rax
  __int64 v7; // rcx

  v4 = CoTaskMemAlloc(0x14u);
  *((_QWORD *)a2 + 4) = v4;
  v5 = v4;
  if ( v4 )
  {
    *((_DWORD *)a2 + 2) = 4109;
    result = 0;
    *((_DWORD *)a2 + 4) = 6;
    v7 = *((_QWORD *)this + 3);
    *(_OWORD *)v5 = *(_OWORD *)v7;
    v5[4] = *(_DWORD *)(v7 + 16);
    *((_DWORD *)a2 + 6) = 20;
    *((_DWORD *)a2 + 1) = 16;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to allocate dynamic memory for packet header info during in-packet processing");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids, "NPSRAD");
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180013808  mov     [rsp+arg_0], rbx
0x18001380d  push    rdi
0x18001380e  sub     rsp, 20h
0x180013812  mov     rdi, rcx
0x180013815  mov     rbx, rdx
0x180013818  mov     ecx, 14h; cb
0x18001381d  call    cs:__imp_CoTaskMemAlloc
0x180013823  mov     [rbx+20h], rax
0x180013827  mov     rdx, rax
0x18001382a  test    rax, rax
0x18001382d  jnz     short loc_180013887
0x18001382f  mov     rax, cs:WPP_GLOBAL_Control
0x180013836  lea     rcx, WPP_GLOBAL_Control
0x18001383d  cmp     rax, rcx
0x180013840  jz      short loc_180013880
0x180013842  cmp     byte ptr [rax+19h], 2
0x180013846  jb      short loc_180013880
0x180013848  test    dword ptr [rax+1Ch], 100h
0x18001384f  jz      short loc_180013880
0x180013851  lea     rcx, aUnableToAlloca; "Unable to allocate dynamic memory for p"...
0x180013858  call    WppDbgPrint
0x18001385d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013864  lea     r9, aNpsrad; "NPSRAD"
0x18001386b  mov     edx, 1Eh
0x180013870  lea     r8, WPP_680dfa5530f83761685653fb6ea5f689_Traceguids
0x180013877  mov     rcx, [rcx+10h]
0x18001387b  call    WPP_SF_s
0x180013880  mov     eax, 8007000Eh
0x180013885  jmp     short loc_1800138B5
0x180013887  mov     dword ptr [rbx+8], 100Dh
0x18001388e  xor     eax, eax
0x180013890  mov     dword ptr [rbx+10h], 6
0x180013897  mov     rcx, [rdi+18h]
0x18001389b  movups  xmm0, xmmword ptr [rcx]
0x18001389e  movups  xmmword ptr [rdx], xmm0
0x1800138a1  mov     ecx, [rcx+10h]
0x1800138a4  mov     [rdx+10h], ecx
0x1800138a7  mov     dword ptr [rbx+18h], 14h
0x1800138ae  mov     dword ptr [rbx+4], 10h
0x1800138b5  mov     rbx, [rsp+28h+arg_0]
0x1800138ba  add     rsp, 20h
0x1800138be  pop     rdi
0x1800138bf  retn
```
