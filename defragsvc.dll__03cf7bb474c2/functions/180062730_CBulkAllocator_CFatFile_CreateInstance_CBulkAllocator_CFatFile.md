# CBulkAllocator<CFatFile>::CreateInstance(CBulkAllocator<CFatFile> * *)

- ea: `0x180062730`
- end: `0x1800627dd`
- name: `?CreateInstance@?$CBulkAllocator@VCFatFile@@@@SAJPEAPEAV1@@Z`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034180`
- `0x180034328`

## callees

- `0x180011e58`
- `0x180043a18`
- `0x180062730`
- `0x180067b0a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180062782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180062782`

## pseudocode

```c
__int64 __fastcall CBulkAllocator<CFatFile>::CreateInstance(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  void *v4; // rax
  __int64 result; // rax

  if ( !a1 )
    return 2147942487LL;
  *a1 = 0;
  v2 = operator new(0x30u);
  v3 = v2;
  if ( v2 )
  {
    *(_DWORD *)v2 = 1;
    v2[1] = 0;
    v2[4] = 24;
    v2[5] = 0;
    v4 = CoTaskMemAlloc(0x80000u);
    v3[1] = v4;
    if ( v4 )
    {
      memset_0(v4, 0, 0x80000u);
      *((_DWORD *)v3 + 4) = 0;
      v3[3] = 0;
      *((_DWORD *)v3 + 5) = 65504;
      result = 0;
      *a1 = v3;
      return result;
    }
    CBulkAllocator<CFatFile>::Release(v3);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x180062730  mov     [rsp+arg_0], rbx
0x180062735  push    rdi
0x180062736  sub     rsp, 20h
0x18006273a  mov     rdi, rcx
0x18006273d  test    rcx, rcx
0x180062740  jz      loc_1800627CD
0x180062746  mov     qword ptr [rcx], 0
0x18006274d  mov     ecx, 30h ; '0'; Size
0x180062752  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062757  mov     rbx, rax
0x18006275a  test    rax, rax
0x18006275d  jz      short loc_1800627C6
0x18006275f  mov     dword ptr [rax], 1
0x180062765  mov     qword ptr [rax+8], 0
0x18006276d  mov     qword ptr [rax+20h], 18h
0x180062775  mov     qword ptr [rax+28h], 0
0x18006277d  mov     ecx, 80000h; cb
0x180062782  call    cs:__imp_CoTaskMemAlloc
0x180062788  mov     [rbx+8], rax
0x18006278c  test    rax, rax
0x18006278f  jz      short loc_1800627BE
0x180062791  xor     edx, edx; Val
0x180062793  mov     r8d, 80000h; Size
0x180062799  mov     rcx, rax; void *
0x18006279c  call    memset_0
0x1800627a1  mov     dword ptr [rbx+10h], 0
0x1800627a8  mov     qword ptr [rbx+18h], 0
0x1800627b0  mov     dword ptr [rbx+14h], 0FFE0h
0x1800627b7  xor     eax, eax
0x1800627b9  mov     [rdi], rbx
0x1800627bc  jmp     short loc_1800627D2
0x1800627be  mov     rcx, rbx
0x1800627c1  call    ?Release@?$CBulkAllocator@VCFatFile@@@@QEAAKXZ; CBulkAllocator<CFatFile>::Release(void)
0x1800627c6  mov     eax, 8007000Eh
0x1800627cb  jmp     short loc_1800627D2
0x1800627cd  mov     eax, 80070057h
0x1800627d2  mov     rbx, [rsp+28h+arg_0]
0x1800627d7  add     rsp, 20h
0x1800627db  pop     rdi
0x1800627dc  retn
```
