# ResolveILinkInfo(_ilinkinfoW const *,ushort *,int,ulong,HWND__ *,ulong *)

- ea: `0x180001780`
- end: `0x180001836`
- name: `?ResolveILinkInfo@@YAHPEBU_ilinkinfoW@@PEAGHKPEAUHWND__@@PEAK@Z`
- size: `182`
- prototype: `__int64 __usercall@<rax>(const struct _ilinkinfoW *@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, unsigned int@<r9d>, HWND, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001670`

## callees

- `0x1800014c0`
- `0x180001780`
- `0x180001840`
- `0x180005240`

## pseudocode

```c
int __fastcall ResolveILinkInfo(
        const struct _ilinkinfoW *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        HWND a5,
        unsigned int *a6)
{
  unsigned int *v6; // r14
  unsigned int v7; // r12d
  int v8; // edi
  int result; // eax
  unsigned int v13; // [rsp+70h] [rbp+18h] BYREF

  v13 = a3;
  v6 = a6;
  v7 = 0;
  v8 = *((_DWORD *)a1 + 2);
  *a6 = 0;
  if ( (v8 & 2) != 0 )
  {
    v13 = 0;
    result = ResolveLocalPathFromServer(a1, a2, &v13);
    v7 = (unsigned __int8)result & v13 & 1;
    if ( result )
      return result;
  }
  else
  {
    result = 0;
  }
  if ( ((v8 & 1) == 0 || (result = ResolveLocalILinkInfo(a1, a2, a3, a4)) == 0) && (v8 & 2) != 0 && !v7 )
    return ResolveRemoteILinkInfo((const CHAR *)a1, a2, a4, a5, v6);
  return result;
}

```

## disassembly

```asm
0x180001780  mov     [rsp+arg_0], rbx
0x180001785  mov     [rsp+arg_8], rbp
0x18000178a  mov     [rsp+arg_10], r8d
0x18000178f  push    rsi
0x180001790  push    rdi
0x180001791  push    r12
0x180001793  push    r14
0x180001795  push    r15
0x180001797  sub     rsp, 30h
0x18000179b  mov     r14, [rsp+58h+arg_28]
0x1800017a3  xor     r12d, r12d
0x1800017a6  mov     edi, [rcx+8]
0x1800017a9  mov     r15d, r9d
0x1800017ac  mov     ebx, edi
0x1800017ae  mov     rbp, rdx
0x1800017b1  mov     rsi, rcx
0x1800017b4  mov     [r14], r12d
0x1800017b7  and     ebx, 2
0x1800017ba  jnz     short loc_1800017EF
0x1800017bc  mov     eax, r12d
0x1800017bf  test    dil, 1
0x1800017c3  jz      short loc_180001810
0x1800017c5  mov     r9d, r15d; unsigned int
0x1800017c8  mov     rdx, rbp; unsigned __int16 *
0x1800017cb  mov     rcx, rsi; struct _ilinkinfoW *
0x1800017ce  call    ?ResolveLocalILinkInfo@@YAHPEBU_ilinkinfoW@@PEAGHK@Z; ResolveLocalILinkInfo(_ilinkinfoW const *,ushort *,int,ulong)
0x1800017d3  test    eax, eax
0x1800017d5  jz      short loc_180001810
0x1800017d7  mov     rbx, [rsp+58h+arg_0]
0x1800017dc  mov     rbp, [rsp+58h+arg_8]
0x1800017e1  add     rsp, 30h
0x1800017e5  pop     r15
0x1800017e7  pop     r14
0x1800017e9  pop     r12
0x1800017eb  pop     rdi
0x1800017ec  pop     rsi
0x1800017ed  retn
0x1800017ef  lea     r8, [rsp+58h+arg_10]; unsigned int *
0x1800017f4  mov     [rsp+58h+arg_10], r12d
0x1800017f9  call    ?ResolveLocalPathFromServer@@YAHPEBU_ilinkinfoW@@PEAGPEAK@Z; ResolveLocalPathFromServer(_ilinkinfoW const *,ushort *,ulong *)
0x1800017fe  mov     r12d, [rsp+58h+arg_10]
0x180001803  and     r12d, 1
0x180001807  and     r12d, eax
0x18000180a  test    eax, eax
0x18000180c  jz      short loc_1800017BF
0x18000180e  jmp     short loc_1800017D7
0x180001810  test    ebx, ebx
0x180001812  jz      short loc_1800017D7
0x180001814  test    r12d, r12d
0x180001817  jnz     short loc_1800017D7
0x180001819  mov     r9, [rsp+58h+arg_20]; HWND
0x180001821  mov     r8d, r15d; unsigned int
0x180001824  mov     rdx, rbp; unsigned __int16 *
0x180001827  mov     [rsp+58h+var_38], r14; unsigned int *
0x18000182c  mov     rcx, rsi; struct _ilinkinfoW *
0x18000182f  call    ?ResolveRemoteILinkInfo@@YAHPEBU_ilinkinfoW@@PEAGKPEAUHWND__@@PEAK@Z; ResolveRemoteILinkInfo(_ilinkinfoW const *,ushort *,ulong,HWND__ *,ulong *)
0x180001834  jmp     short loc_1800017D7
```
