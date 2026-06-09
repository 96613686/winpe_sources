# GetAuditValue(_MI_ConstStringA,ulong *)

- ea: `0x180031f28`
- end: `0x180032088`
- name: `?GetAuditValue@@YA?AW4_MI_Result@@U_MI_ConstStringA@@PEAK@Z`
- size: `352`
- prototype: `enum _MI_Result __fastcall(struct _MI_ConstStringA *__struct_ptr, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012690`
- `0x180031bc0`

## callees

- `0x180031f28`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180031f5e`
- `msvcrt!_wcsicmp` at `0x180031f7b`
- `msvcrt!_wcsicmp` at `0x180031f98`
- `msvcrt!_wcsicmp` at `0x180031fb5`
- `msvcrt!_wcsicmp` at `0x180031fd2`
- `msvcrt!_wcsicmp` at `0x180031fec`
- `msvcrt!_wcsicmp` at `0x180032006`
- `msvcrt!_wcsicmp` at `0x180032020`
- `msvcrt!_wcsicmp` at `0x18003203b`
- `msvcrt!_wcsicmp` at `0x180032050`
- `msvcrt!_wcsicmp` at `0x180031f5e`
- `msvcrt!_wcsicmp` at `0x180031f7b`
- `msvcrt!_wcsicmp` at `0x180031f98`
- `msvcrt!_wcsicmp` at `0x180031fb5`
- `msvcrt!_wcsicmp` at `0x180031fd2`
- `msvcrt!_wcsicmp` at `0x180031fec`
- `msvcrt!_wcsicmp` at `0x180032006`
- `msvcrt!_wcsicmp` at `0x180032020`
- `msvcrt!_wcsicmp` at `0x18003203b`
- `msvcrt!_wcsicmp` at `0x180032050`

## string_xrefs

- `0x180031fe5`: `Delete`
- `0x180031fae`: `Write`
- `0x180031f53`: `Mount`
- `0x180031f74`: `Unmount`
- `0x180031fcb`: `Create`

## pseudocode

```c
__int64 __fastcall GetAuditValue(struct _MI_ConstStringA *a1, unsigned int *a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // ebp
  __int64 i; // r14
  const MI_Char *const *data; // rsi

  v2 = 0;
  v3 = 0;
  for ( i = 0; (unsigned int)i < a1->size; i = (unsigned int)(i + 1) )
  {
    data = a1->data;
    if ( _wcsicmp(L"Mount", a1->data[i]) )
    {
      if ( _wcsicmp(L"Unmount", data[i]) )
      {
        if ( _wcsicmp(L"Read", data[i]) )
        {
          if ( _wcsicmp(L"Write", data[i]) )
          {
            if ( _wcsicmp(L"Create", data[i]) )
            {
              if ( _wcsicmp(L"Delete", data[i]) )
              {
                if ( _wcsicmp(L"Lock", data[i]) )
                {
                  if ( _wcsicmp(L"Unlock", data[i]) )
                  {
                    if ( !_wcsicmp(L"none", data[i]) )
                    {
                      v2 = 0;
                      break;
                    }
                    if ( !_wcsicmp(L"all", data[i]) )
                    {
                      v2 = 255;
                      break;
                    }
                    v3 = 4;
                  }
                  else
                  {
                    v2 |= 0x80u;
                  }
                }
                else
                {
                  v2 |= 0x40u;
                }
              }
              else
              {
                v2 |= 0x20u;
              }
            }
            else
            {
              v2 |= 0x10u;
            }
          }
          else
          {
            v2 |= 8u;
          }
        }
        else
        {
          v2 |= 4u;
        }
      }
      else
      {
        v2 |= 2u;
      }
    }
    else
    {
      v2 |= 1u;
    }
  }
  if ( !v3 )
    *a2 = v2;
  return v3;
}

```

## disassembly

```asm
0x180031f28  push    rbx
0x180031f2a  push    rbp
0x180031f2b  push    rsi
0x180031f2c  push    rdi
0x180031f2d  push    r12
0x180031f2f  push    r14
0x180031f31  push    r15
0x180031f33  sub     rsp, 20h
0x180031f37  xor     ebx, ebx
0x180031f39  xor     ebp, ebp
0x180031f3b  xor     r14d, r14d
0x180031f3e  mov     r15, rdx
0x180031f41  mov     r12, rcx
0x180031f44  cmp     r14d, [r12+8]
0x180031f49  jnb     loc_180032070
0x180031f4f  mov     rsi, [r12]
0x180031f53  lea     rcx, aMount_0; "Mount"
0x180031f5a  mov     rdx, [rsi+r14*8]; String2
0x180031f5e  call    cs:__imp__wcsicmp
0x180031f64  test    eax, eax
0x180031f66  jnz     short loc_180031F70
0x180031f68  or      ebx, 1
0x180031f6b  jmp     loc_18003205F
0x180031f70  mov     rdx, [rsi+r14*8]; String2
0x180031f74  lea     rcx, aUnmount; "Unmount"
0x180031f7b  call    cs:__imp__wcsicmp
0x180031f81  test    eax, eax
0x180031f83  jnz     short loc_180031F8D
0x180031f85  or      ebx, 2
0x180031f88  jmp     loc_18003205F
0x180031f8d  mov     rdx, [rsi+r14*8]; String2
0x180031f91  lea     rcx, aRead; "Read"
0x180031f98  call    cs:__imp__wcsicmp
0x180031f9e  test    eax, eax
0x180031fa0  jnz     short loc_180031FAA
0x180031fa2  or      ebx, 4
0x180031fa5  jmp     loc_18003205F
0x180031faa  mov     rdx, [rsi+r14*8]; String2
0x180031fae  lea     rcx, aWrite; "Write"
0x180031fb5  call    cs:__imp__wcsicmp
0x180031fbb  test    eax, eax
0x180031fbd  jnz     short loc_180031FC7
0x180031fbf  or      ebx, 8
0x180031fc2  jmp     loc_18003205F
0x180031fc7  mov     rdx, [rsi+r14*8]; String2
0x180031fcb  lea     rcx, aCreate; "Create"
0x180031fd2  call    cs:__imp__wcsicmp
0x180031fd8  test    eax, eax
0x180031fda  jnz     short loc_180031FE1
0x180031fdc  or      ebx, 10h
0x180031fdf  jmp     short loc_18003205F
0x180031fe1  mov     rdx, [rsi+r14*8]; String2
0x180031fe5  lea     rcx, aDelete; "Delete"
0x180031fec  call    cs:__imp__wcsicmp
0x180031ff2  test    eax, eax
0x180031ff4  jnz     short loc_180031FFB
0x180031ff6  or      ebx, 20h
0x180031ff9  jmp     short loc_18003205F
0x180031ffb  mov     rdx, [rsi+r14*8]; String2
0x180031fff  lea     rcx, aLock; "Lock"
0x180032006  call    cs:__imp__wcsicmp
0x18003200c  test    eax, eax
0x18003200e  jnz     short loc_180032015
0x180032010  or      ebx, 40h
0x180032013  jmp     short loc_18003205F
0x180032015  mov     rdx, [rsi+r14*8]; String2
0x180032019  lea     rcx, aUnlock; "Unlock"
0x180032020  call    cs:__imp__wcsicmp
0x180032026  test    eax, eax
0x180032028  jnz     short loc_180032030
0x18003202a  bts     ebx, 7
0x18003202e  jmp     short loc_18003205F
0x180032030  mov     rdx, [rsi+r14*8]; String2
0x180032034  lea     rcx, aNone; "none"
0x18003203b  call    cs:__imp__wcsicmp
0x180032041  test    eax, eax
0x180032043  jz      short loc_18003206E
0x180032045  mov     rdx, [rsi+r14*8]; String2
0x180032049  lea     rcx, aAll; "all"
0x180032050  call    cs:__imp__wcsicmp
0x180032056  test    eax, eax
0x180032058  jz      short loc_180032067
0x18003205a  mov     ebp, 4
0x18003205f  inc     r14d
0x180032062  jmp     loc_180031F44
0x180032067  mov     ebx, 0FFh
0x18003206c  jmp     short loc_180032070
0x18003206e  xor     ebx, ebx
0x180032070  test    ebp, ebp
0x180032072  jnz     short loc_180032077
0x180032074  mov     [r15], ebx
0x180032077  mov     eax, ebp
0x180032079  add     rsp, 20h
0x18003207d  pop     r15
0x18003207f  pop     r14
0x180032081  pop     r12
0x180032083  pop     rdi
0x180032084  pop     rsi
0x180032085  pop     rbp
0x180032086  pop     rbx
0x180032087  retn
```
