# CUserModeSynth::Read(void * *,ulong *,ulong *,long *,ulong *,ulong,unsigned __int64 *)

- ea: `0x180012da0`
- end: `0x180012ede`
- name: `?Read@CUserModeSynth@@UEAAJPEAPEAXPEAK1PEAJ1KPEA_K@Z`
- size: `318`
- prototype: `int(CUserModeSynth *__hidden this, void **, unsigned int *, unsigned int *, int *, unsigned int *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006420`
- `0x180012da0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012e61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012eaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012eaf`

## pseudocode

```c
__int64 __fastcall CUserModeSynth::Read(
        CUserModeSynth *this,
        __int16 **a2,
        unsigned int *a3,
        unsigned int *a4,
        int *a5,
        unsigned int *a6,
        unsigned int a7,
        unsigned __int64 *a8)
{
  __int64 v12; // rcx
  CSynth *v14; // rcx
  unsigned int v15; // ebx

  if ( a7 && (!a2 || !a3) )
    return 2147500035LL;
  if ( a7 )
  {
    v12 = 0;
    do
    {
      if ( *(_DWORD *)a8 )
      {
        if ( !a2[v12] )
          return 2147500035LL;
      }
      else if ( !a2[v12] )
      {
        return 2147942487LL;
      }
      v12 = (unsigned int)(v12 + 1);
    }
    while ( (unsigned int)v12 < a7 );
  }
  if ( *a8 > 0xFFFFFFFF || !a7 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 5) )
    return 2289570097LL;
  if ( !*((_DWORD *)this + 14) )
    return 2289570109LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v14 = (CSynth *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    v15 = *(_DWORD *)a8 >> 1;
    CSynth::Mix(v14, a2, a3, a4, a5, a7, *((_DWORD *)this + 17), v15, *((_QWORD *)this + 2));
    *((_QWORD *)this + 2) += v15;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  return 0;
}

```

## disassembly

```asm
0x180012da0  push    rbx
0x180012da2  push    rbp
0x180012da3  push    rsi
0x180012da4  push    rdi
0x180012da5  push    r12
0x180012da7  push    r15
0x180012da9  sub     rsp, 58h
0x180012dad  mov     esi, [rsp+88h+arg_30]
0x180012db4  mov     r12, r9
0x180012db7  mov     r15, r8
0x180012dba  mov     rdi, rdx
0x180012dbd  mov     rbp, rcx
0x180012dc0  test    esi, esi
0x180012dc2  jz      short loc_180012DCE
0x180012dc4  test    rdx, rdx
0x180012dc7  jz      short loc_180012DEB
0x180012dc9  test    r8, r8
0x180012dcc  jz      short loc_180012DEB
0x180012dce  mov     rbx, [rsp+88h+arg_38]
0x180012dd6  test    esi, esi
0x180012dd8  jz      short loc_180012E0E
0x180012dda  mov     edx, [rbx]
0x180012ddc  xor     ecx, ecx
0x180012dde  xchg    ax, ax
0x180012de0  test    edx, edx
0x180012de2  jz      short loc_180012DFD
0x180012de4  cmp     qword ptr [rdi+rcx*8], 0
0x180012de9  jnz     short loc_180012E08
0x180012deb  mov     eax, 80004003h
0x180012df0  add     rsp, 58h
0x180012df4  pop     r15
0x180012df6  pop     r12
0x180012df8  pop     rdi
0x180012df9  pop     rsi
0x180012dfa  pop     rbp
0x180012dfb  pop     rbx
0x180012dfc  retn
0x180012dfd  cmp     qword ptr [rdi+rcx*8], 0
0x180012e02  jz      loc_180012ECC
0x180012e08  inc     ecx
0x180012e0a  cmp     ecx, esi
0x180012e0c  jb      short loc_180012DE0
0x180012e0e  mov     eax, 0FFFFFFFFh
0x180012e13  cmp     [rbx], rax
0x180012e16  ja      loc_180012ECC
0x180012e1c  test    esi, esi
0x180012e1e  jz      loc_180012ECC
0x180012e24  cmp     qword ptr [rbp+28h], 0
0x180012e29  jnz     short loc_180012E3D
0x180012e2b  mov     eax, 88781131h
0x180012e30  add     rsp, 58h
0x180012e34  pop     r15
0x180012e36  pop     r12
0x180012e38  pop     rdi
0x180012e39  pop     rsi
0x180012e3a  pop     rbp
0x180012e3b  pop     rbx
0x180012e3c  retn
0x180012e3d  cmp     dword ptr [rbp+38h], 0
0x180012e41  jnz     short loc_180012E55
0x180012e43  mov     eax, 8878113Dh
0x180012e48  add     rsp, 58h
0x180012e4c  pop     r15
0x180012e4e  pop     r12
0x180012e50  pop     rdi
0x180012e51  pop     rsi
0x180012e52  pop     rbp
0x180012e53  pop     rbx
0x180012e54  retn
0x180012e55  lea     rcx, [rbp+58h]; lpCriticalSection
0x180012e59  mov     [rsp+88h+arg_0], r14
0x180012e61  call    cs:__imp_EnterCriticalSection
0x180012e67  mov     rcx, [rbp+30h]; this
0x180012e6b  test    rcx, rcx
0x180012e6e  jz      short loc_180012EAB
0x180012e70  mov     rax, [rbp+10h]
0x180012e74  mov     r9, r12; unsigned int *
0x180012e77  mov     ebx, [rbx]
0x180012e79  mov     r8, r15; unsigned int *
0x180012e7c  mov     [rsp+88h+var_48], rax; __int64
0x180012e81  mov     rdx, rdi; __int16 **
0x180012e84  mov     eax, [rbp+44h]
0x180012e87  shr     ebx, 1
0x180012e89  mov     [rsp+88h+var_50], ebx; unsigned int
0x180012e8d  mov     [rsp+88h+var_58], eax; unsigned int
0x180012e91  mov     rax, [rsp+88h+arg_20]
0x180012e99  mov     [rsp+88h+var_60], esi; unsigned int
0x180012e9d  mov     [rsp+88h+var_68], rax; int *
0x180012ea2  call    ?Mix@CSynth@@QEAAXPEAPEAFPEAK1PEAJKKK_J@Z; CSynth::Mix(short * *,ulong *,ulong *,long *,ulong,ulong,ulong,__int64)
0x180012ea7  add     [rbp+10h], rbx
0x180012eab  lea     rcx, [rbp+58h]; lpCriticalSection
0x180012eaf  call    cs:__imp_LeaveCriticalSection
0x180012eb5  mov     r14, [rsp+88h+arg_0]
0x180012ebd  xor     eax, eax
0x180012ebf  add     rsp, 58h
0x180012ec3  pop     r15
0x180012ec5  pop     r12
0x180012ec7  pop     rdi
0x180012ec8  pop     rsi
0x180012ec9  pop     rbp
0x180012eca  pop     rbx
0x180012ecb  retn
0x180012ecc  mov     eax, 80070057h
0x180012ed1  add     rsp, 58h
0x180012ed5  pop     r15
0x180012ed7  pop     r12
0x180012ed9  pop     rdi
0x180012eda  pop     rsi
0x180012edb  pop     rbp
0x180012edc  pop     rbx
0x180012edd  retn
```
