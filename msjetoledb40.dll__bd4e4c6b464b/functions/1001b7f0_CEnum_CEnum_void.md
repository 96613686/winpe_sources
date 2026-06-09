# CEnum::~CEnum(void)

- ea: `0x1001b7f0`
- end: `0x1001b885`
- name: `??1CEnum@@QAE@XZ`
- size: `149`
- prototype: `void __thiscall(CEnum *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10024150`
- `0x10024300`

## callees

- `0x1001b7f0`
- `0x1001c6d0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!free` at `0x1001b860`
- `msvcrt!free` at `0x1001b860`
- `KERNEL32!DeleteCriticalSection` at `0x1001b86d`
- `KERNEL32!DeleteCriticalSection` at `0x1001b86d`

## pseudocode

```c
void __thiscall CEnum::~CEnum(CEnum *this)
{
  unsigned int v2; // ebx
  _DWORD *v3; // eax
  int v4; // ecx

  v2 = 0;
  v3 = (_DWORD *)((char *)this + 40);
  if ( *((_DWORD *)this + 1) )
  {
    do
    {
      if ( *v3 )
        v4 = *(_DWORD *)(*(_DWORD *)this + v2 * *((_DWORD *)this + 8) + *((_DWORD *)this + 9));
      else
        v4 = *(_DWORD *)(*(_DWORD *)this + 4 * v2);
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v4 + 8))(*(_DWORD *)(*(_DWORD *)v4 + 8), v4);
      ++v2;
      v3 = (_DWORD *)((char *)this + 40);
    }
    while ( v2 < *((_DWORD *)this + 1) );
    v3 = (_DWORD *)((char *)this + 40);
  }
  if ( *v3 == 1 )
    _free(*(void **)this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 44));
}

```

## disassembly

```asm
0x1001b7f0  mov     edi, edi
0x1001b7f2  push    ebp
0x1001b7f3  mov     ebp, esp
0x1001b7f5  push    0FFFFFFFFh
0x1001b7f7  push    offset ??1CEnum@@QAE@XZ_SEH
0x1001b7fc  mov     eax, large fs:0
0x1001b802  push    eax
0x1001b803  push    ebx
0x1001b804  push    esi
0x1001b805  push    edi
0x1001b806  mov     eax, ___security_cookie
0x1001b80b  xor     eax, ebp
0x1001b80d  push    eax
0x1001b80e  lea     eax, [ebp+var_C]
0x1001b811  mov     large fs:0, eax
0x1001b817  mov     esi, ecx
0x1001b819  xor     ebx, ebx
0x1001b81b  lea     eax, [esi+28h]
0x1001b81e  cmp     [esi+4], ebx
0x1001b821  jbe     short loc_1001B859
0x1001b823  cmp     dword ptr [eax], 0
0x1001b826  jnz     short loc_1001B82F
0x1001b828  mov     eax, [esi]
0x1001b82a  mov     ecx, [eax+ebx*4]
0x1001b82d  jmp     short loc_1001B83D
0x1001b82f  mov     ecx, [esi+20h]
0x1001b832  mov     eax, [esi+24h]
0x1001b835  imul    ecx, ebx
0x1001b838  add     ecx, [esi]
0x1001b83a  mov     ecx, [ecx+eax]
0x1001b83d  mov     eax, [ecx]
0x1001b83f  push    ecx
0x1001b840  mov     edi, [eax+8]
0x1001b843  mov     ecx, edi
0x1001b845  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001b84b  call    edi
0x1001b84d  inc     ebx
0x1001b84e  lea     eax, [esi+28h]
0x1001b851  cmp     ebx, [esi+4]
0x1001b854  jb      short loc_1001B823
0x1001b856  lea     eax, [esi+28h]
0x1001b859  cmp     dword ptr [eax], 1
0x1001b85c  jnz     short loc_1001B869
0x1001b85e  push    dword ptr [esi]; Block
0x1001b860  call    ds:__imp__free
0x1001b866  add     esp, 4
0x1001b869  add     esi, 2Ch ; ','
0x1001b86c  push    esi; lpCriticalSection
0x1001b86d  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1001b873  mov     ecx, [ebp+var_C]
0x1001b876  mov     large fs:0, ecx
0x1001b87d  pop     ecx
0x1001b87e  pop     edi
0x1001b87f  pop     esi
0x1001b880  pop     ebx
0x1001b881  mov     esp, ebp
0x1001b883  pop     ebp
0x1001b884  retn
0x1004e1b0  nop
0x1004e1b1  nop
0x1004e1b2  mov     edx, [esp-4+arg_4]
0x1004e1b6  lea     eax, [edx+0Ch]
0x1004e1b9  mov     ecx, [edx-10h]
0x1004e1bc  xor     ecx, eax; StackCookie
0x1004e1be  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e1c3  mov     eax, offset stru_1004F608
0x1004e1c8  jmp     ___CxxFrameHandler3
```
