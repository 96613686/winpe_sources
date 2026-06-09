# CPropMgr::ComposeHmenuIdentityString(HMENU__ *,ulong,uchar * *,ulong *)

- ea: `0x180023960`
- end: `0x1800239ed`
- name: `?ComposeHmenuIdentityString@CPropMgr@@UEAAJPEAUHMENU__@@KPEAPEAEPEAK@Z`
- size: `141`
- prototype: `__int64 __fastcall(CPropMgr *__hidden this, HMENU, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180019610`
- `0x18001a2a4`
- `0x180023960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800239b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800239b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800239a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800239a0`

## pseudocode

```c
__int64 __fastcall CPropMgr::ComposeHmenuIdentityString(
        CPropMgr *this,
        HMENU a2,
        int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  int v6; // r14d
  unsigned __int8 *v8; // rbx
  unsigned int v9; // ebx
  DWORD CurrentProcessId; // eax
  _BYTE v12[72]; // [rsp+20h] [rbp-48h] BYREF

  v6 = (int)a2;
  OleaccApiCallTrace::OleaccApiCallTrace(v12, 1014, this);
  *a4 = 0;
  *a5 = 0;
  v8 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
  if ( v8 )
  {
    CurrentProcessId = GetCurrentProcessId();
    *(_DWORD *)v8 = -2147483646;
    *((_DWORD *)v8 + 1) = CurrentProcessId;
    *((_DWORD *)v8 + 2) = v6;
    *((_DWORD *)v8 + 3) = a3;
    *a4 = v8;
    v9 = 0;
    *a5 = 16;
  }
  else
  {
    v9 = -2147024882;
  }
  OleaccApiCallTrace::~OleaccApiCallTrace((OleaccApiCallTrace *)v12);
  return v9;
}

```

## disassembly

```asm
0x180023960  push    rbx
0x180023962  push    rbp
0x180023963  push    rsi
0x180023964  push    rdi
0x180023965  push    r14
0x180023967  sub     rsp, 40h
0x18002396b  mov     ebp, r8d
0x18002396e  mov     r14, rdx
0x180023971  mov     r8, rcx
0x180023974  mov     edx, 3F6h
0x180023979  lea     rcx, [rsp+68h+var_48]
0x18002397e  mov     rdi, r9
0x180023981  call    ??0OleaccApiCallTrace@@QEAA@W4OLEACC_API_ENTRYPOINT@@PEAX@Z; OleaccApiCallTrace::OleaccApiCallTrace(OLEACC_API_ENTRYPOINT,void *)
0x180023986  mov     rsi, [rsp+68h+arg_20]
0x18002398e  mov     ecx, 10h; cb
0x180023993  mov     qword ptr [rdi], 0
0x18002399a  mov     dword ptr [rsi], 0
0x1800239a0  call    cs:__imp_CoTaskMemAlloc
0x1800239a6  mov     rbx, rax
0x1800239a9  test    rax, rax
0x1800239ac  jnz     short loc_1800239B5
0x1800239ae  mov     ebx, 8007000Eh
0x1800239b3  jmp     short loc_1800239D6
0x1800239b5  call    cs:__imp_GetCurrentProcessId
0x1800239bb  mov     dword ptr [rbx], 80000002h
0x1800239c1  mov     [rbx+4], eax
0x1800239c4  mov     [rbx+8], r14d
0x1800239c8  mov     [rbx+0Ch], ebp
0x1800239cb  mov     [rdi], rbx
0x1800239ce  xor     ebx, ebx
0x1800239d0  mov     dword ptr [rsi], 10h
0x1800239d6  lea     rcx, [rsp+68h+var_48]; this
0x1800239db  call    ??1OleaccApiCallTrace@@QEAA@XZ; OleaccApiCallTrace::~OleaccApiCallTrace(void)
0x1800239e0  mov     eax, ebx
0x1800239e2  add     rsp, 40h
0x1800239e6  pop     r14
0x1800239e8  pop     rdi
0x1800239e9  pop     rsi
0x1800239ea  pop     rbp
0x1800239eb  pop     rbx
0x1800239ec  retn
```
