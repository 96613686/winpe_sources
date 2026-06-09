# FreeVariant(tagPROPVARIANT *)

- ea: `0x18001cd7c`
- end: `0x18001cdee`
- name: `?FreeVariant@@YAXPEAUtagPROPVARIANT@@@Z`
- size: `114`
- prototype: `void __fastcall(struct tagPROPVARIANT *)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d82c`
- `0x18000db00`
- `0x180011cf0`
- `0x1800129b0`

## callees

- `0x18001cd7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cde7`

## pseudocode

```c
void __fastcall FreeVariant(struct tagPROPVARIANT *a1)
{
  __int64 i; // rsi
  BYTE *pbVal; // rcx

  switch ( a1->vt )
  {
    case 0x1Fu:
      pbVal = a1->pbVal;
      goto LABEL_9;
    case 0x1013u:
      pbVal = a1->bstrblobVal.pData;
LABEL_9:
      CoTaskMemFree(pbVal);
      break;
    case 0x101Fu:
      for ( i = 0; (unsigned int)i < a1->lVal; i = (unsigned int)(i + 1) )
        CoTaskMemFree(*(LPVOID *)&a1->bstrblobVal.pData[8 * i]);
      pbVal = a1->bstrblobVal.pData;
      goto LABEL_9;
  }
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x18001cd7c  mov     [rsp+arg_0], rbx
0x18001cd81  mov     [rsp+arg_8], rsi
0x18001cd86  push    rdi
0x18001cd87  sub     rsp, 20h
0x18001cd8b  movzx   edx, word ptr [rcx]
0x18001cd8e  mov     rbx, rcx
0x18001cd91  sub     edx, 1Fh
0x18001cd94  jz      short loc_18001CDCB
0x18001cd96  sub     edx, 0FF4h
0x18001cd9c  jz      short loc_18001CDC5
0x18001cd9e  cmp     edx, 0Ch
0x18001cda1  jnz     short loc_18001CDD5
0x18001cda3  xor     esi, esi
0x18001cda5  cmp     [rcx+8], esi
0x18001cda8  jbe     short loc_18001CDBF
0x18001cdaa  mov     rcx, [rbx+10h]
0x18001cdae  mov     rcx, [rcx+rsi*8]; pv
0x18001cdb2  call    cs:__imp_CoTaskMemFree
0x18001cdb8  inc     esi
0x18001cdba  cmp     esi, [rbx+8]
0x18001cdbd  jb      short loc_18001CDAA
0x18001cdbf  mov     rcx, [rbx+10h]
0x18001cdc3  jmp     short loc_18001CDCF
0x18001cdc5  mov     rcx, [rcx+10h]
0x18001cdc9  jmp     short loc_18001CDCF
0x18001cdcb  mov     rcx, [rcx+8]; pv
0x18001cdcf  call    cs:__imp_CoTaskMemFree
0x18001cdd5  mov     rcx, rbx
0x18001cdd8  mov     rbx, [rsp+28h+arg_0]
0x18001cddd  mov     rsi, [rsp+28h+arg_8]
0x18001cde2  add     rsp, 20h
0x18001cde6  pop     rdi
0x18001cde7  jmp     cs:__imp_CoTaskMemFree
```
