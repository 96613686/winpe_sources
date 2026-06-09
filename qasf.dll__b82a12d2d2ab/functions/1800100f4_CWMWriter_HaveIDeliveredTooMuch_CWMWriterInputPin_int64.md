# CWMWriter::HaveIDeliveredTooMuch(CWMWriterInputPin *,__int64)

- ea: `0x1800100f4`
- end: `0x18001021e`
- name: `?HaveIDeliveredTooMuch@CWMWriter@@AEAAHPEAVCWMWriterInputPin@@_J@Z`
- size: `298`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, struct CWMWriterInputPin *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014ac0`

## callees

- `0x18000222c`
- `0x1800100f4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800101c7`
- `KERNEL32!SetEvent` at `0x1800101c7`

## pseudocode

```c
__int64 __fastcall CWMWriter::HaveIDeliveredTooMuch(CWMWriter *this, struct CWMWriterInputPin *a2, __int64 a3)
{
  __int64 v3; // rbx
  unsigned int v4; // ebp
  __int64 v8; // r15
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // rcx

  v3 = *((_QWORD *)this + 51);
  v4 = 0;
  if ( v3 )
  {
    do
    {
      v8 = *(_QWORD *)(v3 + 8);
      v9 = *(_QWORD *)(v3 + 16);
      if ( !*(_DWORD *)(v9 + 428) && a2 != (struct CWMWriterInputPin *)v9 )
      {
        if ( a3 >= *(_QWORD *)(v9 + 480) - 3000000LL )
        {
          v10 = *((_QWORD *)this + 51);
          if ( v10 )
          {
            while ( 1 )
            {
              v11 = *(_QWORD *)(v10 + 8);
              v12 = *(_QWORD *)(v10 + 16);
              if ( !*(_DWORD *)(v12 + 428) && (struct CWMWriterInputPin *)v12 != a2 && v12 != v9 )
              {
                v13 = *(_QWORD *)(v9 + 480);
                if ( v13 > *(_QWORD *)(v12 + 488) + 5000000LL
                  && ((unsigned int)(*(_DWORD *)(v12 + 424) - 1) <= 1
                   || v13 > *(_QWORD *)(v12 + 480)
                   && (!(unsigned int)EnableWMFiltersAppCompatibilityOption() || *(_DWORD *)(v12 + 424) != 4)) )
                {
                  break;
                }
              }
              v10 = v11;
              if ( !v11 )
                goto LABEL_15;
            }
          }
          else
          {
LABEL_15:
            SetEvent(*(HANDLE *)(v9 + 336));
          }
        }
        if ( a3 > *(_QWORD *)(v9 + 496) + 5000000LL
          && a3 > *(_QWORD *)(v9 + 480)
          && (!(unsigned int)EnableWMFiltersAppCompatibilityOption() || *(_DWORD *)(v9 + 424) != 4) )
        {
          v4 = 1;
        }
      }
      v3 = v8;
    }
    while ( v8 );
  }
  return v4;
}

```

## disassembly

```asm
0x1800100f4  push    rbx
0x1800100f6  push    rbp
0x1800100f7  push    rsi
0x1800100f8  push    rdi
0x1800100f9  push    r12
0x1800100fb  push    r13
0x1800100fd  push    r14
0x1800100ff  push    r15
0x180010101  sub     rsp, 28h
0x180010105  mov     rbx, [rcx+198h]
0x18001010c  xor     ebp, ebp
0x18001010e  mov     r14, r8
0x180010111  mov     r12, rdx
0x180010114  mov     r13, rcx
0x180010117  test    rbx, rbx
0x18001011a  jz      loc_18001020B
0x180010120  mov     r15, [rbx+8]
0x180010124  mov     rbx, [rbx+10h]
0x180010128  cmp     dword ptr [rbx+1ACh], 0
0x18001012f  jnz     loc_1800101FF
0x180010135  cmp     r12, rbx
0x180010138  jz      loc_1800101FF
0x18001013e  mov     rax, [rbx+1E0h]
0x180010145  sub     rax, 2DC6C0h
0x18001014b  cmp     r14, rax
0x18001014e  jl      short loc_1800101CD
0x180010150  mov     rdi, [r13+198h]
0x180010157  test    rdi, rdi
0x18001015a  jz      short loc_1800101C0
0x18001015c  mov     rsi, [rdi+8]
0x180010160  mov     rdi, [rdi+10h]
0x180010164  cmp     dword ptr [rdi+1ACh], 0
0x18001016b  jnz     short loc_1800101B8
0x18001016d  cmp     rdi, r12
0x180010170  jz      short loc_1800101B8
0x180010172  cmp     rdi, rbx
0x180010175  jz      short loc_1800101B8
0x180010177  mov     rax, [rdi+1E8h]
0x18001017e  mov     rcx, [rbx+1E0h]; unsigned int
0x180010185  add     rax, 4C4B40h
0x18001018b  cmp     rcx, rax
0x18001018e  jle     short loc_1800101B8
0x180010190  mov     eax, [rdi+1A8h]
0x180010196  dec     eax
0x180010198  cmp     eax, 1
0x18001019b  jbe     short loc_1800101CD
0x18001019d  cmp     rcx, [rdi+1E0h]
0x1800101a4  jle     short loc_1800101B8
0x1800101a6  call    ?EnableWMFiltersAppCompatibilityOption@@YAHK@Z; EnableWMFiltersAppCompatibilityOption(ulong)
0x1800101ab  test    eax, eax
0x1800101ad  jz      short loc_1800101CD
0x1800101af  cmp     dword ptr [rdi+1A8h], 4
0x1800101b6  jnz     short loc_1800101CD
0x1800101b8  mov     rdi, rsi
0x1800101bb  test    rsi, rsi
0x1800101be  jnz     short loc_18001015C
0x1800101c0  mov     rcx, [rbx+150h]; hEvent
0x1800101c7  call    cs:__imp_SetEvent
0x1800101cd  mov     rax, [rbx+1F0h]
0x1800101d4  add     rax, 4C4B40h
0x1800101da  cmp     r14, rax
0x1800101dd  jle     short loc_1800101FF
0x1800101df  cmp     r14, [rbx+1E0h]
0x1800101e6  jle     short loc_1800101FF
0x1800101e8  call    ?EnableWMFiltersAppCompatibilityOption@@YAHK@Z; EnableWMFiltersAppCompatibilityOption(ulong)
0x1800101ed  test    eax, eax
0x1800101ef  jz      short loc_1800101FA
0x1800101f1  cmp     dword ptr [rbx+1A8h], 4
0x1800101f8  jz      short loc_1800101FF
0x1800101fa  mov     ebp, 1
0x1800101ff  mov     rbx, r15
0x180010202  test    r15, r15
0x180010205  jnz     loc_180010120
0x18001020b  mov     eax, ebp
0x18001020d  add     rsp, 28h
0x180010211  pop     r15
0x180010213  pop     r14
0x180010215  pop     r13
0x180010217  pop     r12
0x180010219  pop     rdi
0x18001021a  pop     rsi
0x18001021b  pop     rbp
0x18001021c  pop     rbx
0x18001021d  retn
```
