# GetCollectionDesc

- ea: `0x18000cc90`
- end: `0x18000ccf7`
- name: `GetCollectionDesc`
- size: `103`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085d8`
- `0x18000a88c`
- `0x18000ac70`
- `0x18001c924`
- `0x180025f64`
- `0x18003ff7c`
- `0x1800405e4`
- `0x180041d94`

## callees

- `0x18000cc90`
- `0x180021bb0`

## pseudocode

```c
__int64 __fastcall GetCollectionDesc(__int64 a1, int a2)
{
  __int64 v2; // r10
  __int64 v3; // rbx
  __int64 i; // rax

  v2 = *(_QWORD *)(a1 + 160);
  v3 = 0;
  if ( v2 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 168); i = (unsigned int)(i + 1) )
    {
      if ( *(unsigned __int8 *)(v2 + 40 * i + 4) == a2 )
      {
        v3 = v2 + 40 * i;
        if ( !v3 )
          break;
        return v3;
      }
    }
  }
  TraceLoggingGetCollectionDescFailed();
  return v3;
}

```

## disassembly

```asm
0x18000cc90  mov     [rsp+arg_0], rbx
0x18000cc95  push    rdi
0x18000cc96  sub     rsp, 20h
0x18000cc9a  mov     r10, [rcx+0A0h]
0x18000cca1  xor     ebx, ebx
0x18000cca3  mov     r11d, edx
0x18000cca6  mov     rdi, rcx
0x18000cca9  test    r10, r10
0x18000ccac  jz      short loc_18000CCEA
0x18000ccae  mov     r9d, [rcx+0A8h]
0x18000ccb5  xor     eax, eax
0x18000ccb7  cmp     eax, r9d
0x18000ccba  jnb     short loc_18000CCEA
0x18000ccbc  lea     rdx, [rax+rax*4]
0x18000ccc0  movzx   ecx, byte ptr [r10+rdx*8+4]
0x18000ccc6  lea     r8, [r10+rdx*8]
0x18000ccca  cmp     ecx, r11d
0x18000cccd  jnz     short loc_18000CCE6
0x18000cccf  mov     rbx, r8
0x18000ccd2  test    r8, r8
0x18000ccd5  jz      short loc_18000CCEA
0x18000ccd7  mov     rax, rbx
0x18000ccda  mov     rbx, [rsp+28h+arg_0]
0x18000ccdf  add     rsp, 20h
0x18000cce3  pop     rdi
0x18000cce4  retn
0x18000cce6  inc     eax
0x18000cce8  jmp     short loc_18000CCB7
0x18000ccea  mov     edx, r11d
0x18000cced  mov     rcx, rdi
0x18000ccf0  call    TraceLoggingGetCollectionDescFailed
0x18000ccf5  jmp     short loc_18000CCD7
```
