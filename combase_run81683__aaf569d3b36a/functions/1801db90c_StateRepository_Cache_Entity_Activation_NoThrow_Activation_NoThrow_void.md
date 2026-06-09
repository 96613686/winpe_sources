# StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)

- ea: `0x1801db90c`
- end: `0x1801db9bc`
- name: `??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Activation_NoThrow *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18012eebc`

## callees

- `0x1801db90c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db93d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db954`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db96b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db982`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db999`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db9b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db926`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db93d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db954`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db96b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db982`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db999`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801db9b0`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
        StateRepository::Cache::Entity::Activation_NoThrow *this)
{
  wchar_t *value; // rcx
  wchar_t *v3; // rcx
  wchar_t *v4; // rcx
  wchar_t *v5; // rcx
  wchar_t *v6; // rcx
  wchar_t *v7; // rcx
  wchar_t *v8; // rcx

  value = this->m_resourceGroup.__ptr_.__value_;
  this->m_resourceGroup.__ptr_.__value_ = 0;
  if ( value )
    SRCache_Free();
  v3 = this->m_startPage.__ptr_.__value_;
  this->m_startPage.__ptr_.__value_ = 0;
  if ( v3 )
    SRCache_Free();
  v4 = this->m_runtimeType.__ptr_.__value_;
  this->m_runtimeType.__ptr_.__value_ = 0;
  if ( v4 )
    SRCache_Free();
  v5 = this->m_entrypoint.__ptr_.__value_;
  this->m_entrypoint.__ptr_.__value_ = 0;
  if ( v5 )
    SRCache_Free();
  v6 = this->m_executable.__ptr_.__value_;
  this->m_executable.__ptr_.__value_ = 0;
  if ( v6 )
    SRCache_Free();
  v7 = this->m_hostId.__ptr_.__value_;
  this->m_hostId.__ptr_.__value_ = 0;
  if ( v7 )
    SRCache_Free();
  v8 = this->m_activationKey.__ptr_.__value_;
  this->m_activationKey.__ptr_.__value_ = 0;
  if ( v8 )
    SRCache_Free();
}

```

## disassembly

```asm
0x1801db90c  push    rbx
0x1801db90e  sub     rsp, 20h
0x1801db912  mov     rbx, this
0x1801db915  mov     this, [this+40h]
0x1801db919  mov     qword ptr [rbx+40h], 0
0x1801db921  test    this, this
0x1801db924  jz      short loc_1801DB92C
0x1801db926  call    cs:__imp_SRCache_Free
0x1801db92c  mov     this, [rbx+38h]
0x1801db930  mov     qword ptr [rbx+38h], 0
0x1801db938  test    this, this
0x1801db93b  jz      short loc_1801DB943
0x1801db93d  call    cs:__imp_SRCache_Free
0x1801db943  mov     this, [rbx+30h]
0x1801db947  mov     qword ptr [rbx+30h], 0
0x1801db94f  test    this, this
0x1801db952  jz      short loc_1801DB95A
0x1801db954  call    cs:__imp_SRCache_Free
0x1801db95a  mov     this, [rbx+28h]
0x1801db95e  mov     qword ptr [rbx+28h], 0
0x1801db966  test    this, this
0x1801db969  jz      short loc_1801DB971
0x1801db96b  call    cs:__imp_SRCache_Free
0x1801db971  mov     this, [rbx+20h]
0x1801db975  mov     qword ptr [rbx+20h], 0
0x1801db97d  test    this, this
0x1801db980  jz      short loc_1801DB988
0x1801db982  call    cs:__imp_SRCache_Free
0x1801db988  mov     this, [rbx+18h]
0x1801db98c  mov     qword ptr [rbx+18h], 0
0x1801db994  test    this, this
0x1801db997  jz      short loc_1801DB99F
0x1801db999  call    cs:__imp_SRCache_Free
0x1801db99f  mov     this, [rbx+8]
0x1801db9a3  mov     qword ptr [rbx+8], 0
0x1801db9ab  test    this, this
0x1801db9ae  jz      short loc_1801DB9B6
0x1801db9b0  call    cs:__imp_SRCache_Free
0x1801db9b6  add     rsp, 20h
0x1801db9ba  pop     rbx
0x1801db9bb  retn
```
