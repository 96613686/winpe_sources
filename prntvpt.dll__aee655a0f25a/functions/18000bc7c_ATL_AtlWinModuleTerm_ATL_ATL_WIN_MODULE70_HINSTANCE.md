# ATL::AtlWinModuleTerm(ATL::_ATL_WIN_MODULE70 *,HINSTANCE__ *)

- ea: `0x18000bc7c`
- end: `0x18000bd10`
- name: `?AtlWinModuleTerm@ATL@@YAJPEAU_ATL_WIN_MODULE70@1@PEAUHINSTANCE__@@@Z`
- size: `148`
- prototype: `int(struct ATL::_ATL_WIN_MODULE70 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e1dc`

## callees

- `0x18000bc7c`
- `0x18000c394`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18000bcdd`
- `KERNEL32!RaiseException` at `0x18000bcdd`
- `KERNEL32!DeleteCriticalSection` at `0x18000bcf4`
- `KERNEL32!DeleteCriticalSection` at `0x18000bcf4`
- `USER32!UnregisterClassA` at `0x18000bcbf`
- `USER32!UnregisterClassA` at `0x18000bcbf`

## pseudocode

```c
__int64 __fastcall ATL::AtlWinModuleTerm(struct ATL::_ATL_WIN_MODULE70 *a1, HINSTANCE a2)
{
  int v5; // esi
  _QWORD *v6; // rdi

  if ( a1 )
  {
    if ( !*(_DWORD *)a1 )
      return 0;
    if ( *(_DWORD *)a1 == 72 )
    {
      v5 = 0;
      if ( *((int *)a1 + 16) <= 0 )
      {
        v6 = (_QWORD *)((char *)a1 + 56);
      }
      else
      {
        do
        {
          if ( v5 < 0 || (v6 = (_QWORD *)((char *)a1 + 56), v5 >= *((_DWORD *)a1 + 16)) )
          {
            RaiseException(0xC000008C, 1u, 0, 0);
            __debugbreak();
          }
          UnregisterClassA((LPCSTR)*(unsigned __int16 *)(*v6 + 2LL * v5++), a2);
        }
        while ( v5 < *((_DWORD *)a1 + 16) );
      }
      ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(v6);
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 8));
      *(_DWORD *)a1 = 0;
      return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000bc7c  push    rbx
0x18000bc7e  push    rbp
0x18000bc7f  push    rsi
0x18000bc80  push    rdi
0x18000bc81  sub     rsp, 28h
0x18000bc85  mov     rbp, rdx
0x18000bc88  mov     rbx, rcx
0x18000bc8b  test    rcx, rcx
0x18000bc8e  jz      short loc_18000BD02
0x18000bc90  cmp     dword ptr [rcx], 0
0x18000bc93  jnz     short loc_18000BC99
0x18000bc95  xor     eax, eax
0x18000bc97  jmp     short loc_18000BD07
0x18000bc99  cmp     dword ptr [rcx], 48h ; 'H'
0x18000bc9c  jnz     short loc_18000BD02
0x18000bc9e  xor     esi, esi
0x18000bca0  cmp     [rcx+40h], esi
0x18000bca3  jle     short loc_18000BCE4
0x18000bca5  test    esi, esi
0x18000bca7  js      short loc_18000BCCE
0x18000bca9  lea     rdi, [rbx+38h]
0x18000bcad  cmp     esi, [rdi+8]
0x18000bcb0  jge     short loc_18000BCCE
0x18000bcb2  mov     rax, [rdi]
0x18000bcb5  mov     rdx, rbp; hInstance
0x18000bcb8  movsxd  rcx, esi
0x18000bcbb  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x18000bcbf  call    cs:__imp_UnregisterClassA
0x18000bcc5  inc     esi
0x18000bcc7  cmp     esi, [rbx+40h]
0x18000bcca  jl      short loc_18000BCA5
0x18000bccc  jmp     short loc_18000BCE8
0x18000bcce  xor     r9d, r9d; lpArguments
0x18000bcd1  xor     r8d, r8d; nNumberOfArguments
0x18000bcd4  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000bcd9  lea     edx, [r9+1]; dwExceptionFlags
0x18000bcdd  call    cs:__imp_RaiseException
0x18000bce3  int     3; Trap to Debugger
0x18000bce4  lea     rdi, [rcx+38h]
0x18000bce8  mov     rcx, rdi
0x18000bceb  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18000bcf0  lea     rcx, [rbx+8]; lpCriticalSection
0x18000bcf4  call    cs:__imp_DeleteCriticalSection
0x18000bcfa  mov     dword ptr [rbx], 0
0x18000bd00  jmp     short loc_18000BC95
0x18000bd02  mov     eax, 80070057h
0x18000bd07  add     rsp, 28h
0x18000bd0b  pop     rdi
0x18000bd0c  pop     rsi
0x18000bd0d  pop     rbp
0x18000bd0e  pop     rbx
0x18000bd0f  retn
```
