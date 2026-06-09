# CDirectMusic::UpdatePortList(void)

- ea: `0x180013ed4`
- end: `0x18001402e`
- name: `?UpdatePortList@CDirectMusic@@QEAAJXZ`
- size: `346`
- prototype: `__int64 __fastcall(CDirectMusic *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800131a0`
- `0x180013460`
- `0x180013654`

## callees

- `0x1800012c4`
- `0x18000a56c`
- `0x180012e60`
- `0x180013ed4`
- `0x18001afa8`
- `0x18001e9c4`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusic::UpdatePortList(CDirectMusic *this)
{
  char *v1; // rdi
  __int64 i; // rax
  __int64 result; // rax
  int (__high *v5)(void *, struct _DMUS_PORTCAPS *, enum PORTTYPE, int, int, int, HKEY); // rdx
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rbp
  __int64 v9; // rsi
  char *v10; // rsi
  __int64 v11; // rdi
  __int64 v12; // rcx

  v1 = (char *)this + 32;
  for ( i = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 4) + 40LL))((char *)this + 32); i; i = *(_QWORD *)(i + 8) )
    *(_DWORD *)(*(_QWORD *)(i + 16) + 4LL) = 0;
  result = EnumerateUMADevices(this);
  if ( (int)result >= 0 )
  {
    result = EnumLegacyDevices(this, v5);
    if ( (int)result >= 0 )
    {
      result = CDirectMusic::AddSoftwareSynths(this);
      if ( (int)result >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v1 + 40LL))(v1);
        if ( v6 )
        {
          while ( 1 )
          {
            v7 = *(_QWORD *)(v6 + 16);
            if ( !v7 )
              break;
            v8 = *(_QWORD *)(v6 + 8);
            if ( !*(_DWORD *)(v7 + 4) )
            {
              v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v7 + 344) + 40LL))(v7 + 344);
              if ( v9 )
              {
                while ( 1 )
                {
                  v11 = *(_QWORD *)(v9 + 8);
                  if ( !v11 )
                    break;
                  v12 = *(_QWORD *)(v11 + 16);
                  if ( !v12 )
                    break;
                  operator delete(*(void **)(v12 + 16));
                  operator delete(*(void **)(v11 + 16));
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)(v6 + 16) + 344LL) + 16LL))(
                    *(_QWORD *)(v6 + 16) + 344LL,
                    v9);
                  v9 = v11;
                }
                return 2289570146LL;
              }
              v10 = *(char **)(v6 + 16);
              if ( v10 )
              {
                CList<tagPORTDEST *>::~CList<tagPORTDEST *>(v10 + 344);
                operator delete(v10);
              }
              (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v1 + 16LL))(v1, v6);
            }
            v6 = v8;
            if ( !v8 )
              return (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v1 + 48LL))(v1) == 0;
          }
          return 2289570146LL;
        }
        else
        {
          return (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)v1 + 48LL))(v1) == 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013ed4  push    rbx
0x180013ed6  push    rbp
0x180013ed7  push    rsi
0x180013ed8  push    rdi
0x180013ed9  sub     rsp, 28h
0x180013edd  lea     rdi, [rcx+20h]
0x180013ee1  mov     rbx, rcx
0x180013ee4  mov     rax, [rdi]
0x180013ee7  mov     rcx, rdi
0x180013eea  mov     rax, [rax+28h]
0x180013eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ef3  jmp     short loc_180013F04
0x180013ef5  mov     rcx, [rax+10h]
0x180013ef9  mov     dword ptr [rcx+4], 0
0x180013f00  mov     rax, [rax+8]
0x180013f04  test    rax, rax
0x180013f07  jnz     short loc_180013EF5
0x180013f09  mov     rcx, rbx; struct CDirectMusic *
0x180013f0c  call    ?EnumerateUMADevices@@YAJPEAVCDirectMusic@@@Z; EnumerateUMADevices(CDirectMusic *)
0x180013f11  test    eax, eax
0x180013f13  js      loc_180013FD6
0x180013f19  mov     rcx, rbx; void *
0x180013f1c  call    ?EnumLegacyDevices@@YAJPEAXP6AJ0AEAU_DMUS_PORTCAPS@@W4PORTTYPE@@HHHPEAUHKEY__@@@Z@Z; EnumLegacyDevices(void *,long (*)(void *,_DMUS_PORTCAPS &,PORTTYPE,int,int,int,HKEY__ *))
0x180013f21  test    eax, eax
0x180013f23  js      loc_180013FD6
0x180013f29  mov     rcx, rbx; this
0x180013f2c  call    ?AddSoftwareSynths@CDirectMusic@@QEAAJXZ; CDirectMusic::AddSoftwareSynths(void)
0x180013f31  test    eax, eax
0x180013f33  js      loc_180013FD6
0x180013f39  mov     rax, [rdi]
0x180013f3c  mov     rcx, rdi
0x180013f3f  mov     rax, [rax+28h]
0x180013f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f48  mov     rbx, rax
0x180013f4b  test    rax, rax
0x180013f4e  jz      short loc_180013FBE
0x180013f50  mov     rcx, [rbx+10h]
0x180013f54  test    rcx, rcx
0x180013f57  jz      loc_180014027
0x180013f5d  cmp     dword ptr [rcx+4], 0
0x180013f61  mov     rbp, [rbx+8]
0x180013f65  jnz     short loc_180013FB6
0x180013f67  add     rcx, 158h
0x180013f6e  mov     rax, [rcx]
0x180013f71  mov     rax, [rax+28h]
0x180013f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f7a  mov     rsi, rax
0x180013f7d  test    rax, rax
0x180013f80  jnz     short loc_180013FDF
0x180013f82  mov     rsi, [rbx+10h]
0x180013f86  test    rsi, rsi
0x180013f89  jz      short loc_180013FA4
0x180013f8b  lea     rcx, [rsi+158h]
0x180013f92  call    ??1?$CList@PEAUtagPORTDEST@@@@UEAA@XZ; CList<tagPORTDEST *>::~CList<tagPORTDEST *>(void)
0x180013f97  mov     edx, 378h; unsigned __int64
0x180013f9c  mov     rcx, rsi; void *
0x180013f9f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013fa4  mov     rax, [rdi]
0x180013fa7  mov     rdx, rbx
0x180013faa  mov     rcx, rdi
0x180013fad  mov     rax, [rax+10h]
0x180013fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fb6  mov     rbx, rbp
0x180013fb9  test    rbp, rbp
0x180013fbc  jnz     short loc_180013F50
0x180013fbe  mov     rax, [rdi]
0x180013fc1  mov     rcx, rdi
0x180013fc4  mov     rax, [rax+30h]
0x180013fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fcd  xor     ecx, ecx
0x180013fcf  test    eax, eax
0x180013fd1  setz    cl
0x180013fd4  mov     eax, ecx
0x180013fd6  add     rsp, 28h
0x180013fda  pop     rdi
0x180013fdb  pop     rsi
0x180013fdc  pop     rbp
0x180013fdd  pop     rbx
0x180013fde  retn
0x180013fdf  mov     rdi, [rsi+8]
0x180013fe3  test    rdi, rdi
0x180013fe6  jz      short loc_180014027
0x180013fe8  mov     rcx, [rdi+10h]
0x180013fec  test    rcx, rcx
0x180013fef  jz      short loc_180014027
0x180013ff1  mov     rcx, [rcx+10h]; void *
0x180013ff5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013ffa  mov     rcx, [rdi+10h]; void *
0x180013ffe  mov     edx, 20h ; ' '; unsigned __int64
0x180014003  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014008  mov     rcx, [rbx+10h]
0x18001400c  mov     rdx, rsi
0x18001400f  add     rcx, 158h
0x180014016  mov     rax, [rcx]
0x180014019  mov     rax, [rax+10h]
0x18001401d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014022  mov     rsi, rdi
0x180014025  jmp     short loc_180013FDF
0x180014027  mov     eax, 88781162h
0x18001402c  jmp     short loc_180013FD6
```
